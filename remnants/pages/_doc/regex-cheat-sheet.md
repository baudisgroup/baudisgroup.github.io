---
title: "Some Regular Expressions and more..."
date: 2018-07-20
layout: default
author: Michael
excerpt_separator: <!--more-->
pdf_file_name:
pdf_file_type:    # slides poster article
www_link: 
www_links_formatted:   # use this for a quoted, complete HTML link with label '<a href="http://" target="_blank">...</a>'
category: 
  - howto      # publication howto presentation
tags: 
  - code
  - markdown
  - regex
  - Perl
---

## {{ page.title }}

This page contains some regular expressions which have come in handy during our work. Code is in __Perl__ style syntax.
<!--more-->


##### Converting Foswiki / TkWiki Links to Markdown

Some Wikis use a `[[_link_][_label_]]` notion, e.g. `[[http://progenetix.org][Progenetix resource]]`. The following regular expression swaps those to Markdown links `[Progenetix resource](http://progenetix.org)`, assuming they don't have a `]` in their link or label...:

```
/\[\[([^\]]+?)\]\[([^\]]+?)\]\]/[\2](\1)/g
```

##### Converting Markdown links to HTML

The following regular expression Markdown links `[Progenetix resource](http://progenetix.org)` to HTML code, assuming there are no `]` or `)` in link or label...:

```
/\[([^\]]+?)\]\(([^\)]+?)\)/<a href="$2" target="_BLANK">$1</a>/g
```

##### Swapping columns in a file

This is a nifty Perl one-liner, to re-arrange columns in a text file. Taken from a [post on StackOverflow](https://stackoverflow.com/a/31176824/1863431)...

In the example, `-F\\t` is for "tab-delimited"; `@F[1,0,2..$#F]` leads to columns (rather values per line) 1 and 2 being swapped (i.e. index 0 and 1), and 3 to last being left in place.

```
perl -F\\t -nlae 'print join("\t", @F[1,0,2..$#F])' inputfile
```

Based on this example it should also be easy to remove columns or change the delimiter...
