[![Build Status](https://travis-ci.org/dpeuscher/util.svg?branch=master)](https://travis-ci.org/dpeuscher/util) [![codecov](https://codecov.io/gh/dpeuscher/util/branch/master/graph/badge.svg)](https://codecov.io/gh/dpeuscher/util)
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fdpeuscher%2Futil.svg?type=shield)](https://app.fossa.io/projects/git%2Bgithub.com%2Fdpeuscher%2Futil?ref=badge_shield)

# util
Code that extends existing basic PHP-functionality

```php
$from = '5'; // possible also: '1.5.', '5-1', '2018-05-01'
$to = '7';

$dateHelper = new DateHelper();
list($fromDateTime, $toDateTime) = $dateHelper->buildDateTimeRangeFromTwoInputs($from, $to);
// Default $to is generated by third parameter as DateInterval:
// list($fromDateTime, $toDateTime) = $dateHelper->buildDateTimeRangeFromTwoInputs($from, null, 'P2M');


var_export([$fromDateTime->format('Y-m'), $toDateTime->format('Y-m')]);
```
Result looks like this: (given today is 2018)
> array (
    0 => '2018-05-01',
    1 => '2018-08-01',
  )

```php
$dateHelper = new DateHelper();
$date = $dateHelper->buildDateTimeSince('P3D'); // Interval param defaults to P7D = 1 week - will use P1D if not parsable

print($date->format('Y-m-d'));
```
Result looks like this: (given today is 2018-05-01)
> 2018-05-04
  
```php
$dateHelper = new DateHelper();
$text = $dateHelper->diffToText(new DateInterval('P3DPT4H5M6S'));

print($text);
```
Result looks like this:
> 3d 4h 5m 6s


```php
$text = StringHelper::trim('Longtext', 5);

print($text);
```
Result looks like this:
> Longt...


```php
$text = StringHelper::shortenNameToFirst('John Doe');

print($text);
```
Result looks like this:
> John D



## License
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fdpeuscher%2Futil.svg?type=large)](https://app.fossa.io/projects/git%2Bgithub.com%2Fdpeuscher%2Futil?ref=badge_large)