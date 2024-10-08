# typescript-template

A launching point for a TypeScript repository

## Requirements

- [NodeJS](https://nodejs.org)
- [VSCode](https://code.visualstudio.com/)

  - To enable [Editor SDK](https://yarnpkg.com/getting-started/editor-sdks), run

    ```sh
    yarn dlx @yarnpkg/sdks vscode
    ```

    Then in TypeScript file, simultaneously press

    `ctrl` + `shift` + `p`

    and choose option

    `Select TypeScript Version`

    then select value

    `Use Workspace Version`

## Install

To install dependencies, run

```sh
yarn install
```

## Custom Types

Some external modules do not contain typing information, either lacking it baked-in or not having a `@types/<mondule_name>` package. To provide typings for such repositories, add a `typings/<module_name>.d.ts` file with contents similar to:

```ts
declare module '<module_name>' {
  export function get(): string
  export function set(item: string): void
}
```

with appropriate declarations for exports of that module. If you don't know the exports (or don't want to take the time/effort to write them down), the file can simply contain:

```ts
declare module '<module_name>'
```

which will allow you to work with `<module_name>` as an `any` type within your code.

## Run

To execute source code, run

```sh
yarn start
```

The script takes the following environment variables:

| Name | Required | Default | Description | Example(s) |
| ---- | -------- | ------- | ----------- | ---------- |
| FOO  | No       | bar     | `buzz`      |            |

## Build

To compile typescript into javascript, run

```sh
yarn build
```

To execute the compiled javascript, run

```sh
node build/index.js
```

## Lint

To lint code for programmatic and stylistic error detection, run

```sh
yarn lint
```
