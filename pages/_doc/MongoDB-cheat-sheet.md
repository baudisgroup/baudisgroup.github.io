---
title:  "MongoDB Cheat Sheet"
permalink: /howto/mongodbcommands/
layout: default
date: 2021-02-03
excerpt_separator: <!--more-->
category:
  - howto
tags:
  - mongodb
  - code
---

## MongoDB Cheat Sheet

As frequent-but-not-every-day-one-needs-these-command [MongoDB](http://mongodb.org) users, we, obviously, can use a cheat sheet. Here is the start of one.

#### List all (primary) attributes

Since not all documents may have all keys, the following method loops over all documents and collects the encountered keys.

```javascript
var dbks = {};
db.___your-collection-name___.find().forEach(function(doc){Object.keys(doc).forEach(function(key){allKeys[key]=1})})
dbks;
```

<!--more-->

#### Delete fields with `undefined` from nested list

This procedure rewrites the list objects for the other keys, excluding here the `description` key if the value is "undefined":

```
db.biosamples.find({}).forEach(function(item)
	{
		for(i = 0; i != item.biocharacteristics.length; ++i) {
			if (item.biocharacteristics[i].description == null) {
				item.biocharacteristics[i] = { id: item.biocharacteristics[i].id, label : item.biocharacteristics[i].label }
			}
		}
		db.biosamples.update({_id: item._id}, item);
	}
)
```

#### Rename a collection

This is done via an admin command, using the full path (i.e. "database.collection").
**Destructive**, if `_NewCollection_` exists (when using `dropTarget: true`).

```javascript
db.adminCommand( { renameCollection:"_database_._OldCollection_", to: "_database_._NewCollection_", dropTarget: true } )
```

#### Count distinct values with a condition

In this example the count of distinct values for `pmid` is shown, vor all samples having a partial match of "CVCL" in their `cellosaurusid`.

```
db.samples.distinct("pmid",{"cellosaurusid":{$regex:/CVCL/i}}).length
```

#### Count distinct values with a condition, from a nested object in a list

This calls for an aggregation, where:

* the list is unwound
* the values are collected (`$group` into `_id`)
* a match is performed
* the number of the resulting objects is counted

```
db.biosamples.aggregate(
	{
		$unwind: "$external_references"
	},
	{
		$group:{
			_id:"$external_references.id",
		}
	},
	{
		$match:{
			_id:{"$regex":/PMID/}
		}
	},
	{
		$count: "pubmeds"
	}
)
```
