---
title: "Array Re-shuffling in Perl"
date: 2018-07-20
layout: default
author: mbaudis
excerpt_separator: <!--more-->
pdf_file_name:
pdf_file_type:    # slides poster article
www_link:
www_links_formatted:   # use this for a quoted, complete HTML link with label '<a href="http://" target="_blank">...</a>'
category:
  - howto      # publication howto presentation
tags:
  - code
  - Perl
---

## {{ page.title }}

This dependency-free array randomiser will return a re-shuffled array or
a slice of random $iL array elements.

<!--more-->

The `$overSamp` factor is "empirical" and balances between oversampling with
out-of-range values + filtering, and cycling too many times to match all
index elements.

```
sub RandArr {

=pod
## RandI

#### Expects:

* an array reference of arbitrary content
* the number of array elements to be returned (optional)

#### Return

* the re-shuffled array or a subset of its elements (as array reference)

This dependency-free array randomiser will return a re-shuffled array(ref) or
a slice of random $iL array elements.

The $overSamp factor is "empirical" and balances between oversampling with
out-of-range values + filtering, and cycling too many times to match all
index elements.

=cut

  my $arr       =   shift;
  my $iL        =   shift;
  my $overSamp  =   7;

  if (ref $arr ne 'ARRAY') { return \0 }

  # if no number of array elements => all
  if ($iL !~ /^\d+?$/) {
    $iL = scalar @$arr }
  # ... not more than all
  elsif ($iL > @$arr) {
    $iL = scalar @$arr }

  $overSamp *= $iL;

  # maximum index number, for filtering the oversampled values
  my $maxI      =   @$arr - 1;
  if ($maxI < 0) { return \0 }

  # use of a hash to have unique index numbers (keys of the hash)
  my %randNo    =   ();

  # adding to the hash keys until equal or more than needed
  while (keys %randNo < $iL) {
    %randNo     =   map{ $_ => 1 } (grep{ $_ <= $maxI } (keys %randNo, map{ int(rand($_)) } 0..$overSamp) );
  }

  return [ @$arr[ (keys %randNo)[0..($iL-1)] ] ];

}
```

This is a simple example of how to call the sub...

Setting the `-randno` parameter to a positive integer would produce an array slice of `n` elements.

```
#!/usr/bin/perl

$| = 1;

# CPAN packages
use PGX::Helpers::UtilityLibs;

my %args        =   @ARGV;
$args{'-randno'}    ||= -1;   # imiting on number of returned array elements

my $arr         =  [ a .. z,  A .. Z, 0 .. 9 ];   # some values ...
$arr            =  RandArr($arr, $args{'-randno'});

print join(' :: ', @$arr)."\n";
```
