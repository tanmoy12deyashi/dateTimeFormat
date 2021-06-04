# easydatetimeformat
A lightweight node.js package for formatting Date & Time in easy way.
<br />_Source File < 5kb_


# Installation
```bash
$ npm install easydatetimeformat
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
dateTimeFormat(new Date('02-12-2020'), 'ddd MMM yyyy')  // 12th Feb 2020
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

### Format Options

| Format    | Format Description                                                                                                                                                             |
|-----------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `d`       | Day of the month as digits; no leading zero for single-digit days. (1, .. ,31)                                                                                                 |
| `dd`      | Day of the month as digits; leading zero for single-digit days. (01, .. ,31)                                                                                                   |
| `ddd`     | Day of the month as ordinal number. (1st, 2nd, 3rd, 4th, .. ,31st)                                                                                                             |
| `DDD`     | Day of the week as a three-letter abbreviation.  (Sun, ... Sat)                                                                                                                 |
| `DDDD`    | Day of the week as its full name  (Sunday, ... Saturday)                                                                                                                       |
| `m`       | Month as digits; no leading zero for single-digit months.  (1, .. ,12)                                                                                                         |
| `mm`      | Month as digits; leading zero for single-digit months.    (01, .. ,12)                                                                                                         |
| `MMM`     | Month as a three-letter abbreviation. (Jan, ...., Dec)                                                                                                                         |
| `MMMM`    | Month as its full name.     (January, ...., December)                                                                                                                           |
| `yy`      | Year as last two digits                                                                                                                                                         |
| `yyyy`    | Year represented by four digits.                                                                                                                                               |
| `h`       | Hours; no leading zero for single-digit hours                                                                                                                                   |
| `hh`      | Hours; leading zero for single-digit hours                                                                                                                                     |
| `i`       | Minutes; no leading zero for single-digit minutes.                                                                                                                             |
| `ii`      | Minutes; leading zero for single-digit minutes.                                                                                                                                 |
| `s`       | Seconds; no leading zero for single-digit seconds.                                                                                                                             |
| `ss`      | Seconds; leading zero for single-digit seconds.                                                                                                                                 |
| `A`       | AM or PM.                                                                                                                                                                       |
