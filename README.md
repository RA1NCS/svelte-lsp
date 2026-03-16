# svelte-lsp

Claude Code plugin providing Svelte language server integration. Gives Claude LSP-powered code intelligence on `.svelte` files: go-to-definition, hover docs, find references, document symbols, and diagnostics.

## Install

```bash
npx svelte-lsp-claude
```

Then restart Claude Code.

<details>
<summary>Manual install</summary>

```bash
npm install -g svelte-language-server
claude plugin marketplace add RA1NCS/svelte-lsp
claude plugin install svelte-lsp@svelte-lsp
```

</details>

## What it does

Registers `svelteserver --stdio` as the LSP server for `.svelte` files. Once installed, Claude can use the LSP tool for:

| Operation | Use case |
|-----------|----------|
| `hover` | Type info, prop definitions, component docs |
| `goToDefinition` | Jump to where a symbol is defined |
| `findReferences` | Find all usages of a variable/component |
| `documentSymbol` | List all symbols in a component |
| `goToImplementation` | Find interface implementations |

The plugin also includes a `CLAUDE.md` that instructs Claude to proactively use LSP when working with Svelte files.

## Requirements

- Node.js 16+
- `svelte-language-server` installed globally (`npm install -g svelte-language-server`)
- Claude Code with plugin support

## How it works

Claude Code's plugin system reads the `lspServers` field from `plugin.json` at startup to register language servers for file extensions. This plugin maps `.svelte` files to `svelteserver --stdio`, the same LSP server VS Code uses for Svelte.

## License

MIT
