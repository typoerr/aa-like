# aa-like

Like async/await implementation using by Generator.

## Example

```js
import aa from 'aa-like';

function* g(n: number) {
    const n1: number = yield Promise.resolve(n + 10);
    const n2: [number, number] = yield Promise.all([n1 + 10, n1 + 10]);
    return n2.reduce((x, y) => x + y);
}

const exec = aa(g);
exec(1).then(v => assert.equal(v, 42));
```