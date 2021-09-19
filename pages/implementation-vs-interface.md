# Implementation vs Interface

## Implementation

- How something **works**
- E.g., **add** a method to push an element onto a stack
- **Concrete**
- Details **exposed**
- Usually **difficult** (but not always)

### Example

```
// implement the push method
Stack.prototype.push = function(elt) {
  this.items.push(elt);
}
```

## Interface

- How something **is used**
- E.g., **use** a method to push an element onto a stack
- **Abstract**
- Details are **hidden**
- Usually **easy** (but not always)

### Example

```
var stack = new Stack();
// use the push method
stack.push(13);
```
