This repo demonstrates an issue with dependency detection in `.cjs` files.

Run `nx lint` and you will see an error that `lodash` is not used, even though it is in `src/foo.cjs` file (and `src/foo.cts`).

Uncomment the import in either `src/bar.mjs` or `src/bar.mts`, and you will see the error go away.

This error happens because the file graph does not indicate `npm:lodash` as a dependency of `src/foo.cjs`.
