# BOZ Redux game definition

Data that describes _Call of Duty: Black Ops Zombies_ 1.0.11 (Android) for the BOZ Redux client
and SDK: names and addresses of game functions, the game's data layouts, its events and its
console. It contains no game code or assets; it is knowledge recovered by reverse engineering.

| File                         | Contents                                                                     |
| ---------------------------- | ---------------------------------------------------------------------------- |
| `gamedef.toml`               | Manifest: schema version, game versions, file list                           |
| `symbols/boz-1.0.11.toml`    | Named functions, globals, structs and virtual slots (image offsets)          |
| `reflection/boz-1.0.11.toml` | Every reflected class: bases and fields (offset, size, type)                 |
| `events/boz-1.0.11.toml`     | Observer events (`SUBJECT_*`): ids and the classes that send and handle them |
| `console/boz-1.0.11.toml`    | Console variables and developer commands                                     |

## Creation Notes

This was created with a human steered Generative AI (LLM) setup, minimal human verification was done besides functionality tests.

## Who uses it

- **[boz-redux](https://github.com/ZappaVinny/boz-redux)** (the client) pins this repo as a
  submodule. Its mod runtime resolves names, fields and events from it.
- **[boz-redux-sdk](https://github.com/ZappaVinny/boz-redux-sdk)** generates it from the Ghidra
  project and its tools, and uses it in bozkit.

Edit it through the SDK (see its `docs/reverse-engineering.md`), not by hand. A change that
breaks readers bumps `schema` in `gamedef.toml`.

## License

MIT (see `LICENSE`). The game itself belongs to Activision and is not covered or included.
