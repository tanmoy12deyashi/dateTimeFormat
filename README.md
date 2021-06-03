# easydatetimeformat
A lightweight node.js package for formatting Date & Time in easy way.


# Installation
```bash
$ npm install easydatetimeformat
$ easydatetimeformat --help
```

# How To Use

##### Import Module
```js
var { dateTimeFormat } = require("easydatetimeformat");
or
var dateTimeFormat = require("easydatetimeformat").dateTimeFormat;
```
##### Basic Format
```js
// get default format [dd-mm-yyyy]
dateTimeFormat();
or dateTimeFormat('now');
or dateTimeFormat(new Date());
or dateTimeFormat(1622658600000);
or dateTimeFormat('03-06-2021'); //dd-mm-yyyy
or dateTimeFormat('03-06-21'); //dd-mm-yy
or dateTimeFormat('2021-06-03'); //yyyy-mm-dd
// 03-06-2021 [dd-mm-yyyy]
```
##### Get Custom Format
```js
// get user defined format
dateTimeFormat('now', 'dd-mm-yyyy hh:ii:ss');
// 03-06-2021 23:35:04

dateTimeFormat('now', 'dd-mm-yyyy hh:ii:ss A');
or dateTimeFormat(new Date, 'dd-mm-yyyy hh:ii:ss A');
or dateTimeFormat(new Date(), 'dd-mm-yyyy hh:ii:ss A');
or dateTimeFormat(1622743639156, 'dd-mm-yyyy hh:ii:ss A');
//03-06-2021 11:37:19 PM

dateTimeFormat('12-2-2020', 'ddd MMM yyyy');  //12th Feb 2020
dateTimeFormat('12-2-20', 'ddd MMM yyyy');  //12th Feb 2020
dateTimeFormat('2020-2-12', 'ddd MMM yyyy');  //12th Feb 2020
```

##### Set Format
```js
// input date type --> date-month-year
dateTimeFormat('02-12-2020', 'ddd MMM yyyy');  //2nd Dec 2020
dateTimeFormat('02-12-20', 'ddd MMM yyyy');  //2nd Dec 2020
dateTimeFormat('02-12-2020', 'ddd MMM yyyy', '%d%m%y');  //2nd Dec 2020
dateTimeFormat('02-12-20', 'ddd MMM yyyy', '%d%m%y');  //2nd Dec 2020


// input date type --> year-month-date
dateTimeFormat('2020-12-23', 'ddd MMMM yyyy');  // 23rd December 2020
dateTimeFormat('2020-12-23', 'ddd MMMM yyyy', '%y%m%d');  // 23rd December 2020
dateTimeFormat('20-12-23', 'ddd MMMM yyyy', '%y%m%d');  // 23rd December 2020


// input date type --> month-date-year
dateTimeFormat('02-12-2020', 'ddd MMM yyyy', '%m%d%y'); // 12th Feb 2020
dateTimeFormat('02-12-20', 'ddd MMM yyyy', '%m%d%y');  // 12th Feb 2020
```

##### Some Friendly Error
```js
// input date type --> date-month-year
dateTimeFormat('53-12-2020', 'ddd MMM yyyy');  // Invalid Date
dateTimeFormat('5-13-2020', 'ddd MMM yyyy');  // Invalid Month
dateTimeFormat('5-12-20202', 'ddd MMM yyyy');  // Invalid Year
dateTimeFormat('5-12-2020-20', 'ddd MMM yyyy');  // Invalid Format
and so on...
```

##### Any Type of Date Separator [dot(.) comma(,) dash(-) slash(/) blank( ) underscore(_)]
```js
// input date type --> date-month-year
dateTimeFormat('5.12.2020', 'ddd MMM yyyy');
or dateTimeFormat('5-12-2020', 'ddd MMM yyyy');
or dateTimeFormat('5 12 2020', 'ddd MMM yyyy');
or dateTimeFormat('5,12,2020', 'ddd MMM yyyy');
or dateTimeFormat('5/12/2020', 'ddd MMM yyyy');
or dateTimeFormat('5_12_2020', 'ddd MMM yyyy');
// 5th Dec 2020
```