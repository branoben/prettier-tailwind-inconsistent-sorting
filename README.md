# Description

An example repository to show inconsistent sorting using Prettier with Tailwind plugin.

Running the Prettier --write command produces different result when specifying a file vs running Prettier on all files.
Therefore, after saving and formatting a file in VS Code, the Prettier format check on all files using CLI fails.

# Installation

```
pnpm install
```

# Reproducing the issue

## Formatting a single file

```
pnpm prettier --write "test.html" --config prettier.config.mjs
```

(or `pnpm format-file`)

Produces the following result:

```
<div class="before:[mask-image:--variable] before:[mask-size:contain]"></div>
```

## Formatting all files

```
pnpm prettier --write . --config prettier.config.mjs
```

(or `pnpm format-all`)

Produces the following result:

```
<div class="before:[mask-size:contain] before:[mask-image:--variable]"></div>
```
