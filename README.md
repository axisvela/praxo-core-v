# PRAXO-CORE for V

V implementation of the PRAXO-CORE contract. This repository is the VPM
distribution of the V Core from
[axisvela/praxo-core](https://github.com/axisvela/praxo-core).

- `SPEC_VERSION`: `0.2.0`
- Package: `praxo-core`
- Core version: `0.1.2`
- Import: `import praxo`
- Tier: core
- License: MIT

## Install

```bash
v install praxo-core
```

## Scope

`0.1.2` implements all eleven conformance vector groups: tool-call parsing,
JSON Schema, plugin manifests, memory, events, stream kinds, checkpoint
envelopes, path policy, context budgets, middleware, and the agent loop.
Provider adapters and plugin hosts remain follow-up work.

## API

```v
import praxo

call := praxo.parse_tool_call('<tool_call name="echo">{"text":"hi"}</tool_call>') or {
	panic(err)
}
assert call.name == 'echo'
```

Public declarations are inventoried in [`api/0.1.2.txt`](api/0.1.2.txt).

## Layout

- `praxo/` package source.
- `v.mod` package metadata.
- `api/` public API snapshot.
- `SETUP.md` local toolchain notes.

## Release tags

This repository uses plain semantic-version tags such as `0.1.2`; the main
monorepo uses `v/v0.1.2`.
