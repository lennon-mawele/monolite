# Monolite
> Structural-sharing tree modifier

**Monolite** is a little JavaScript library that permits to modify a tree by stuctural-sharing preserving tree immutability.

```js
import { set } from 'monolite'

const summerTree = {
  firstLeaf: 'green',
  lastLeaf: 'green'
}

const autumnTree = set(summerTree, _ => _.firstLeaf)('yellow')
```

`summerTree` is still the same object as declared:
```js
{
  firstLeaf: 'green',
  lastLeaf: 'green'
}
```

`autumnTree` shares structure with `summerTree` except for `firstLeaf` which has been set to `'yellow'`
```js
{
  firstLeaf: 'yellow',
  lastLeaf: 'green'
}
```

## TypeScript
The main motivation of this library is to preserve static-typing, type-inference and completion provided by TypeScript, which is broken when using Immutable.js `fromJSON`.

Monolite takes Plain-Old JavaScript Objects and returns Plain-Old JavaScript Objects. Accessors permit TypeScript to understand the types you're dealing with and to provide completion and linting as if you were working directly on these objects.


## Development

### Build
The build process involves **TypeScript** and **Babel**.

```sh
gulp build
```

### Test
Will run tests using Mocha

```sh
gulp test
```

### Development mode
Will watch source and build and run tests automatically on update.

```sh
gulp dev
```
