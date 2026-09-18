# index-driven-docs

A lightweight ChatGPT skill for creating documentation trees whose paths describe meaning while index files describe structure and reading order.

The skill favors semantic file and directory names, per-level indexes, relative navigation, and synchronized documentation structure. It avoids numeric ordering prefixes and does not mix its index-driven model with a competing navigation scheme for the same documentation tree.

## Main idea

Instead of:

```text
docs/
├── 01-overview.md
├── 02-architecture.md
└── 03-deployment.md
```

prefer:

```text
docs/
├── index.md
├── overview.md
├── architecture.md
└── deployment.md
```

and express navigation and reading order in `index.md`.

Nested documentation levels receive their own index files, while asset-only directories are exempt.

## Files

- `SKILL.md` — installable skill definition.
- `LICENSE` — MIT License.
