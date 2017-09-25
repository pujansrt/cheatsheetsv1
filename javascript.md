
## Generators

```javascript
function* sillyGenerator() {
    yield 1;
    yield 2;
    yield 3;
}

var gen = sillyGenerator();
console.log(gen.next()); // { value: 1, done: false }
console.log(gen.next()); // { value: 2, done: false }
console.log(gen.next()); // { value: 3, done: false }
console.log(gen.next()); // { value: undefined, done: true }
```

Generators can be used to convert async operations to sync

```javascript
function request(url) {
    getJSON(url, function(response) {
        generator.next(response);
    });
}
// And here we write a generator function that will return our data:

function* getData() {
    var entry1 = yield request('http://some_api/item1');
    var entry2 = yield request('http://some_api/item2');
}
```

## Debounce
Using Lodash libarary
Creates a debounced function that delays invoking func until after wait milliseconds have elapsed since the last time the debounced function was invoked. The debounced function comes with a cancel method to cancel delayed func invocations and a flush method to immediately invoke them.

```javascript
_.debounce(func, [wait=0], [options={}])

// Avoid costly calculations while the window size is in flux.
jQuery(window).on('resize', _.debounce(calculateLayout, 150));
 
// Invoke `sendMail` when clicked, debouncing subsequent calls.
jQuery(element).on('click', _.debounce(sendMail, 300, {
  'leading': true,
  'trailing': false
}));
```