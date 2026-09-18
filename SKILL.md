---
name: index-driven-docs
description: Use for new documentation trees to keep file and directory names semantic, represent hierarchy and reading order through per-directory index files, and avoid conflicting navigation schemes.
---

# Index-driven docs

Use this skill when creating a new documentation tree, including a new documentation subtree inside an existing project.

The core rule is simple: paths describe meaning; index files describe structure and order.

## Scope

Use `docs/` as the default documentation root for a new general-purpose project unless another root is more appropriate.

If documentation is itself the project's primary deliverable, the project root may serve as the documentation root instead of adding a redundant `docs/` directory.

If an existing project already has a clear documentation-root convention, follow it.

Do not retrofit an existing documentation tree merely to satisfy this skill.

## Index every documentation level

Every directory that participates in the documentation hierarchy must have an index file.

Use `index.md` for Markdown-oriented documentation and `index.html` for HTML-oriented documentation by default. If the project has a clear alternative convention for index filenames, follow that convention.

A directory that contains only supporting assets such as images, stylesheets, scripts, or downloadable resources does not need an index unless it also participates as a documentation level.

For mixed Markdown and HTML trees, choose the index format that matches the primary format of that documentation level.

## Index responsibilities

Each index must:

- briefly state the purpose and scope of its documentation level;
- link to every direct human-facing document in that directory;
- link to every direct child documentation directory through that child's index;
- briefly state the role of each listed document or child documentation level;
- express recommended reading order when one exists;
- otherwise state when a document is useful when that context is not already obvious from its role.

Keep these descriptions as short as navigation allows. Do not duplicate document summaries unnecessarily.

The presentation is flexible. Lists, tables, headings, or other suitable structures are all acceptable.

A nested index must also provide a relative link back to its parent index.

Individual documents do not need a backlink to their local index unless another project rule requires one.

## Keep paths semantic

Name files and directories for their content or role.

Do not encode presentation order or reading order into file or directory names with prefixes such as `01-`, `02-`, or similar numbering.

Numbers are allowed when they are semantically meaningful, such as a protocol version, RFC number, phase identifier, or other real part of the subject.

If a filename needs `and` to combine independent responsibilities, prefer splitting the content into separate documents. Keep a combined name when the joined phrase represents a single natural concept, such as `terms-and-conditions`.

Do not impose a casing convention such as kebab-case or snake_case unless the project already has one.

## Keep navigation canonical

Within a documentation tree governed by this skill, its index hierarchy is the canonical navigation structure.

A direct document belongs canonically to its nearest parent index. Higher-level indexes should link to child indexes rather than duplicating their descendant documents as structural entries. Supplemental cross-links are allowed when useful.

Use relative links within the documentation tree.

Ensure the project's primary entry point links to the documentation root index. If a new project has no suitable primary entry point yet, create one appropriate to the project type and link it to the documentation root.

## Keep indexes synchronized

Whenever a document or documentation directory is added, removed, moved, or renamed, update every affected index in the same change.

Verify both directions:

- every document and child documentation directory listed by an index exists;
- every direct human-facing document and child documentation directory is represented by its parent index;
- child-directory links resolve to the child's index;
- no broken navigation links remain.

Also update reading-order or usage guidance when the structural change affects it.

## Avoid competing navigation schemes

Do not combine this scheme with another manually maintained navigation scheme for the same documentation tree when that other scheme already defines document membership, hierarchy, or reading order.

Do not disable this skill merely because a documentation generator or related tool is present. Treat it as a conflict only when another source is actually managing the same navigation responsibilities.

If a conflicting navigation scheme governs the target documentation tree, do not apply this skill there. Report that the skill was not applied and why.

A separate, independent documentation tree in the same project may still use this skill.

For cases that do not fit these rules cleanly, ask the user rather than expanding the skill with speculative compatibility rules.
