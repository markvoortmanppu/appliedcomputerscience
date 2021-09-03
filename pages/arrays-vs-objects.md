# Arrays vs Objects

## Arrays

- Store **values**
- Access by **index**

### Constructor

```
var arr = []; // preferred
new Array();
```

### Access

```
// access by index

arr[13]; // use bracket notation

var tmp = 13; // tmp stores index
var arr[tmp]; // retrieve value
```

### Loop

```
var arr = [1, 2, 3];
for (var i = 0; i < arr.length; i++) {
  var value = arr[i];
  console.log(value);
}
```

## Objects

- Store **key-value pairs**
- Access by **key**

### Constructor

```
var obj = {};
new Stack(); // or other data type
```

### Access

```
// access by key

obj.key; // use dot notation
obj["key"]; // use bracket notation

var tmp = "key"; // tmp stores key
obj[tmp]; // retrieve value
```

### Loop

```
var obj = { a: 1, b: 2, c: 3 };
for (var key in obj) {
  var value = obj[key];
  console.log(key + " " + value);
}
```
