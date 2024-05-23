# cheat-sheets

## Typescript

### Type Guards

#### typeof
```ts
type num = number | string;

const add = (a: num, b: num) {
  if (typeof a === "number" && typeof b === "number") {
    return a + b; // a - number, b - number
  }
}
```
