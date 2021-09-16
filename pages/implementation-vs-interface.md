# Implementation vs Interface

## Implementation

- How something **works**
- E.g., **add** a method to push an element onto a stack
- **Concrete**
- Details **exposed**
- Usually **difficult**

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
- Usually **easier**

### Example

```
var stack = new Stack();
// use the push method
stack.push(13);
```
