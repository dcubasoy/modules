# Installation

- download and copy `session.js` into the `/modules/` directory __or create a definition with:__

```javascript
const options = {};

// Counting of XHR requests (default: true):
// options.xhr = true;

// Tracks all online IP addresses (default: false)
// options.ip = true;

// A default URL address of statistics (only for package)
// options.url = '/webcounter/';

INSTALL('module', 'https://cdn.totaljs.com/webcounter.js', options);
```

## Instance

```javascript
var webcounter = MODULE('webcounter');
```

### Online visitors

`console.log(webcounter.online);`

### Today statistics

`console.log(webcounter.today);`

### Instance

`console.log(webcounter.instance);`

## Helpers

- Get online visitors `@{online()}`
- Get count of all unique visitors `@{visitors()}`

## Additional features

### Blacklist

- URL which start with `/your/url/` will be skipped

```javascript
MODULE('webcounter').blacklist('/your/url/');
```

### Custom counter

#### Append into statistics:

```javascript
// These are counters which are visible on monitor.totaljs.com
MODULE('webcounter').increment('orders'); // Increment order counter
MODULE('webcounter').increment('users'); // Increment user counter
MODULE('webcounter').increment('fulltext'); // Increment fulltext search counter
MODULE('webcounter').increment('custom'); // Increment custom counter

// Or create your custom counter, e.g.
MODULE('webcounter').increment('contact-form'); // Increment contact form counter
```

#### Read from statistics:

Show today orders, you can apply this example for all counters. e.g. `MODULE('webcounter').today.YOUR_COUNTER`

```javascript
console.log(MODULE('webcounter').today.orders);
// or
console.log(MODULE('webcounter').today['contact-form']);
```

#### Extend request instance

```javascript
req.webcounter; // datetime (last visited "date", first visit: "null")
```