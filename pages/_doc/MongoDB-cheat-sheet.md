---
title:  "MongoDB Cheat Sheet"
permalink: /howto/mongodbcommands/
layout: default
date: 2019-11-06
category:
  - howto
tags:
  - mongodb
  - code
---

## MongoDB Cheat Sheet

As frequent-but-not-every-day-one-needs-these-command [MongoDB](http://mongodb.org) users, we, obviously, can use a cheat sheet. Here is the start of one.

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
			_id:"$external_references.type.id",
		}
	},
	{
		$match:{
			_id:{"$regex":/pubmed/}
		}
	},
	{
		$count: "pubmeds"
	}
)
```
