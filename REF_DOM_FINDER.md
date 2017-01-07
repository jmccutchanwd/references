# DOM Finder

This is the quickest way to pinpoint a DOM element from the Body.

## Load DOM into a const
```

const domX = document.body.children; //loads DOM Tree into Array

console.log(domX);

```
This puts the DOM into an array. 

Console log it, and open it up. You will see a list of nodes.

## Select a Node
```

const domX = document.body.children; //loads DOM Tree into Array
let elX = domX[3];//drills down to child node

console.log(domX, elX);

```
## Children of the Child
```

const domX = document.body.children; //loads DOM Tree into Array
let elX = domX[3].children[1];//drills down to child node, than its child

console.log(domX, elX);

```
If the element that you need is inside a node, open the node in the console,
and scroll down to children. There will be a 'HTML Collection' in an array.

Find the child you want and add .children[x] to domX[x].
