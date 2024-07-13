# proposal-destructuring-private

A proposal to integrate private fields and destructuring.

```js
class Foo {
  #x = 1;

  constructor() {
    console.log(this.#x); // => 1
    
    const { #x: x } = this;
    console.log(x); // => 1
  }

  equals({ #x: otherX }) {
    const { #x: currentX } = this;
    return currentX === otherX;
  }
}
```

## Champions

- Justin Ridgewell ([@jridgewell](https://github.com/jridgewell/))

## Status

Current [Stage](https://tc39.es/process-document/): 2

## Motivation

Destructuring is a popular feature to store local references to an
object's properties. Private Field's proposal targeted the minimum
features needed to support the goal of private properties in class
instances. Unfortunately, this left destructuring out.

This proposal avoids questions of reification of Private Fields by
limiting this to syntax only. It also doesn't need to worry about
"shorthand" syntax (`#x` in an expression being shorthand for
`this.#x`), because the Committee has decided we will not persue
shorthand syntax after the [Ergonomic Brand Checks][ergo-brand-check]
Proposal.

## Related

- https://github.com/tc39/proposal-class-fields/issues/4

[ergo-brand-check]: https://github.com/tc39/proposal-private-fields-in-in
