# proposal-destructuring-private

A proposal integrate private fields and destructuring.

```js
class Foo {
  #x = 1;

  constructor() {
    console.log(this.#x); // => 1
    
    const { #x: x } = this;
    console.log(x); // => "1"
  }
}
```

## Champions

- Justin Ridgewell ([@jridgewell](https://github.com/jridgewell/))

## Status

Current [Stage](https://tc39.es/process-document/): 0

## Motivation


## Related

- https://github.com/tc39/proposal-class-fields/issues/4
