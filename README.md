# webstorm-import-symlink
> debugging auto import with symlinks in webstorm

## Setup
Execute `npm install` inside the project root.

## Issue
Auto imports don't respect Typescript's `preserveSymlinks` flag.
To reproduce the issue, remove the import statement from `src/main/index.ts` and use Webstorms auto import functionality. 

### Expected result
The import should be resolved to the `@test/target` directory inside `src/main/node_modules`:
`import { testTarget } from "@test/target";`.

Additional information: execute `npm run expected` to see Typescript's output with the `preserveSymlinks` flag.

### Actual result
The import is resolved to the `src/target/` directory.
`import { testTarget } from "../target/index";`.

Additional information: execute `npm run actual` to see Typescript's output without the `preserveSymlinks` flag.
