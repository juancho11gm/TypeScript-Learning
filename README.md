# TypeScript

TypeScriptis a strict syntactical superset of JavaScript.

## Types by Inference

```js
let helloWorld = 'Hello World';
// let helloWorld: string
// TypeScript knows that helloWorld is a string.
```

## Defining Types

```js
interface User {
	name: string;
	id: number;
}

// variables
const user: User = {
	name: 'Juan',
	id: 1,
};

// classes
class UserAccount {
	name: string;
	id: number;

	constructor(name: string, id: number) {
		this.name = name;
		this.id = id;
	}
}
const user: User = new UserAccount('Juan', 1);

// functions
function getAdminUser(): User {
	//...
}
```

`type` and `interface` act the same for the most common cases. However, `interface` use is recommended over `type`.

- TypeScript can provide terser and more focused when working with interfaces.
- Interfaces are open. This means they can extend an interface by declaring it a second time.

```js
interface Kitten {
	purrs: boolean;
}

interface Kitten {
	colour: string;
}
```

## Composing Types

Create complex types by combining simple ones.

```js
type WindowStates = 'open' | 'closed' | 'minimized';

function getLength(obj: string | string[]) {
	return obj.length;
}
```

## Generics

```js
type ObjectWithNameArray = Array<{ name: string }>;
```

## Structural Type System

```js
interface Point {
	x: number;
	y: number;
}

function logPoint(p: Point) {
	console.log(`${p.x}, ${p.y}`);
}

const point = { x: 12, y: 26 };
logPoint(point);

const rect = { x: 33, y: 3, width: 30, height: 80 };
logPoint(rect); // logs "33, 3"

const color = { hex: '#187ABF' };
logPoint(color); // Argument of type '{ hex: string; }' is not assignable to parameter of type 'Point'.
```

# Docs

- [TypeScript for JavaScript programmers](https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes.html)
