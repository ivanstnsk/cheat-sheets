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

#### instanceof
```ts
class Box {
  private side: number = 10;

  getSide = (): number => {
    return this.side;
  }
}

class Circle {
  private radius: number = 10;

  getRadius = (): number => {
    return this.radius;
  }
}

type Figure = Box | Circle;

const render = (figure: Figure) => {
  let size: number = 0;

  if (figure instanceof Box) {
    size = figure.getSide();  // figure - Box
  }
  if (figure instanceof Circle) {
    size = figure.getRadius(); // figure - Circle
  }
}
```

#### in type
```ts
const render = (figure: Figure) => {
  let size: number = 0;

  if ('getSide' in figure) {
    size = figure.getSide(); // figure - Box
  }
  if ('getRadius' in figure) {
    size = figure.getRadius(); // figure - Circle
  }
}
```

#### equality narrowing
```ts
const check = (a: number | string, b: number) => {
  if (a === b) {
    // a - number because b - number
  } else {
    // a - number | string
  }
}
```
