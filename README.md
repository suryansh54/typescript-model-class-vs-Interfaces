# TypeScript Interfaces vs Model Class

Model Class | Interfaces
--- | ---
An interface is only used by TypeScript at `compile time`, and is then removed. Interfaces do not end up in our final JavaScript output. | `Runtime`

## Interfaces
#### Interface Example 01:
```javascript
export interface IProduct {
    ProductNumber: number;
    ProductName: string;
    ProductDescription: string;
}
```

#### Interface Example 02:
```javascript
interface Duck {
    // ...a `hasWings` property with the value `true` (boolean literal type)
    hasWings: true
    // ...a `noOfFeet` property with the value `2` (number literal type)
    noOfFeet: 2
    // ...a `quack` method which does not return anything
    quack(): void
}

// This would pass type-checking!
const duck: Duck = {
    hasWings: true,
    noOfFeet: 2,
    quack() {
        console.log('Quack!')
    },
}

// This would not pass type-checking as it does not
// correctly implement the Duck interface.
const notADuck: Duck = {}
// The TypeScript compiler would tell us
// "Type '{}' is not assignable to type 'Duck'.
// Property 'hasWings' is missing in type '{}'."``javascript
```

## Model Class
#### Model Class Example 01:
```javascript
export class Product {
    constructor(
        public ProductNumber: number,
        public ProductName: string,
        public ProductDescription: string
    ){}
}
```
