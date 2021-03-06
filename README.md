# Tick

A tiny time format lib

### install

```bash
npm i tickjs -S
```

### Usage

As CommonJS module
```javascript
const Tick = require('tickjs');

const today = new Tick().format('YYYY-MM-DD');
```

As ES module
```javascript
import Tick from 'tickjs';

const today = new Tick().format('YYYY-MM-DD');
```

### Documentation

**Paramters**

Tick inherit [Date instance](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date). So the paramters are the same as Date instance.

**Methods**

##### format(template)
- Arguments:
  - {string} template
- Usage:
  Format a time template string.
  ```javascript
  new Tick().format('YYYY-MM-DD');
  // YYYY -> Year
  // WW -> Week
  // MM -> Month
  // DD -> Day
  // Md -> Month(no zero on head)
  // Dd -> Day(no zero on head)
  // hh -> Hour
  // mm -> Minute
  // ss -> Second
  ```

##### getMap()
- Usage:
  Get the object of time.
  ```javascript
  new Tick().getMap(); // { year: '..', month: '..', day: '..', ... }
  ```

##### getDiff()
- Usage:
  Get the description of time difference.
  ```javascript
  new Tick(Date.now() - 20000000).getDiff(); // 5小时前
  ```

##### offset(timeOffset)
- Arguments:
  - {string} timeOffset
- Usage:
  calculate time offset.
  ```javascript
  new Tick('2018-05-01').offset('1Y'); // '2019-05-01T00:00:00.000Z'
  new Tick('2018-05-01').offset('-1Y1M'); // '2017-04-01T00:00:00.000Z'
  ```

##### isBefore(time)
- Arguments:
  - {string} time
- Usage:
  compare time.
  ```javascript
  new Tick('2018-05-01').isBefore('2018-06-01'); // true
  ```

##### isAfter(time)
- Arguments:
  - {string} time
- Usage:
  compare time.
  ```javascript
  new Tick('2018-05-01').isAfter('2018-04-01'); // true
  ```

##### isEqual(time)
- Arguments:
  - {string} time
- Usage:
  compare time.
  ```javascript
  new Tick('2018-05-01').isEqual('2018-05-01'); // true
  ```

##### isLeapYear(year)
- Arguments:
  - {string} year
- Usage:
  check year is leap year.
  ```javascript
  Tick.isLeapYear(2018) // false
  ```

### LICENSE
MIT
