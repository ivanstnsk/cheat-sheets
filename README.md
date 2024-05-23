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
  } else if (figure instanceof Circle) {
    size = figure.getRadius(); // figure - Circle
  }
}
```
