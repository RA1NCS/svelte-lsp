# Svelte LSP Plugin

You have `svelte-language-server` available for `.svelte` files via the LSP tool.

## When to use

Use the LSP tool on `.svelte` files for:
- **`hover`** - get type info, prop definitions, component docs before making changes
- **`goToDefinition`** - find where components, variables, stores are defined
- **`findReferences`** - find all usages before renaming or refactoring
- **`documentSymbol`** - get an overview of a component's structure (script vars, markup elements)
- **`goToImplementation`** - find concrete implementations of interfaces/types

## Proactive usage

- Before editing a `.svelte` component, use `documentSymbol` to understand its structure
- Before renaming a prop or variable, use `findReferences` to find all usages
- When importing a component, use `hover` on it to check its expected props
- When debugging type errors, use `hover` to inspect inferred types

## Prerequisites

The user must have `svelte-language-server` installed globally:
```bash
npm install -g svelte-language-server
```

If LSP calls return "No LSP server available", prompt the user to install it.
