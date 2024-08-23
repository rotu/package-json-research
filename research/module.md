# module

This describes the main entry point for ESM packages.
Historically, `main` has been the *only* way to declare a package's modules to Node. Node more recently supports the more flexible `exports`.
In the meantime, bundlers converged around adding top-level field, with the most common being `module`, though this was never adopted by `node`.

Where used by bundlers `module` is used in parallel with top-level `main`, `browser`, et al. These are collectively referred to as `mainFields`.[^2]

The Node docs [mention this field](https://github.com/nodejs/node/blob/9edf4a0856681a7665bd9dcf2ca7cac252784b98/doc/api/packages.md?plain=1#L889-L893), saying that `node` does not support it.

## Tooling

- This field is [described on SchemaStore](https://github.com/SchemaStore/schemastore/blob/c668421350214c96b249771ca37678b8c7877584/src/schemas/json/package.json#L755-L758) as "An ECMAScript module ID that is the primary entry point to your program."
- This field is included in DefinitelyTyped[^3]
- This field is unused by Node.js 20.17.0, Bun 1.1.25, and Deno 1.46.1.
- This field is unused by npm.
- This field is supported by yarn documented as deprecated by yarn, recommending to use the top-level `exports` field instead [^1]
- Supported universally by bundlers (checked rollup, webpack, vite, parcel, esbuild)

[^1]: https://yarnpkg.com/configuration/manifest#module
[^2]: [rollup](https://github.com/rollup/plugins/blob/8550c4b1925b246adbd3af48ed0e5f74f822c951/packages/node-resolve/README.md?plain=1#L126-L132), [webpack](https://github.com/webpack/webpack/blob/09543e7d8e0e7dd1703207193bcc3c3252874636/declarations/WebpackOptions.d.ts#L1619-L1622), [vite](https://github.com/vitejs/vite/blob/561b940f6f963fbb78058a6e23b4adad53a2edb9/docs/config/shared-options.md?plain=1#L142-L147)
[^3]: https://github.com/DefinitelyTyped/DefinitelyTyped/blob/78c20f65b205e1c6af590a685921aeb796747ee4/types/npmcli__package-json/index.d.ts#L365-L369
