## primitives
- primitive types (aka scalar or simple types)
	- fit into memory easily
- JS has 6 primitive types
	- null
	- undefined
	- Boolean
	- Number
	- String
	- Symbol **

## reference types
- reference types (aka complex or container types)
	- can contain multiple values
- reference types in JS include:
	- Object
	- Array
	- Function

## falsy values in JS
- null
- NaN
- false
- 0
- ""

## Error Handling

JavaScript can handle errors in code:

```
try {
  eaten += garden[y][x];  // might be out-of-bounds
} catch (err) {
  // can now print `err`, or do something different
  eaten = 0;
}
```

You can also throw errors to indicate a problem:

```
function getHighestGrade(tests) {
  if (tests.length === 0) {
    throw new Error("No tests provided!");
  }
  // ... rest of code follows ...
}
```

This is often much clearer than returning a “magic” value, like `-1` or undefined.