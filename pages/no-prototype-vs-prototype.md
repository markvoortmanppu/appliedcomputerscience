# No Prototype vs Prototype

[Here is a video that converts a no-prototype queue implementation into a prototype one](videos/cmps-260-no-prototype-vs-prototype.mp4).

## No Prototype

- Properties are defined with **var**
- Properties are referenced as **variableName**
- Methods are defined **inside** the constructor
- Methods are defined **without** the prototype
- **Inefficient** because methods are **not shared**

### Example Definition

```
function Example() {
  var property = "No prototype.";
  this.getProperty = function() {
    return property;
  };
}
```

### Example Usage (Identical)

```
var example = new Example();
console.log(example.getProperty());
// prints "No prototype."
```

## Prototype

- Properties are defined with **this**
- Properties are referenced as **this.variableName**
- Methods are defined **outside** the constructor
- Methods are defined **with** the prototype
- **Efficient** because methods are **shared**

### Example Definition

```
function Example() {
  this.property = "Prototype.";
}

Example.prototype.getProperty = function() {
  return this.property;
};
```

### Example Usage (Identical)

```
var example = new Example();
console.log(example.getProperty());
// prints "Prototype."
```
