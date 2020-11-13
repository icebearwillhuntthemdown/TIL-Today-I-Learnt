# Null Safe Operators

## `?.` : Optional chaining
```typescript
let x = foo?.bar.baz()
let x = foo === null || foo === undefined ? undefined : foo.bar.baz();
```

## `??` : Nullish coalescing
```typescript
let x = foo ?? bar();
lex x = foo !== null && foo !== undefined ? foo : bar()
```

coalesce : combine elements in a whole

## References
- [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Optional_chaining)
- [Typescript](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-3-7.html)
