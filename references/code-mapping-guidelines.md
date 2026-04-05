# Code Mapping Guidelines

Use this file only when repository analysis is truly worth writing into the note.

## Goal

Map the paper's workflow diagrams, key formulas, and implementation path into a readable Chinese explanation.

The goal is not to explain the whole repository. The goal is to show how the paper lands in code.

## When to write code mapping

Write this part only if:

- the repository clearly matches the paper
- there is direct evidence for module / formula / training-flow mapping
- the mapping adds explanatory value to the note

Skip it when the repository is weakly aligned, too generic, incomplete, or not helpful.

## Default mapping order

1. overall workflow diagram ↔ code entry path
2. key formulas ↔ implementation blocks
3. tensor shape changes / forward path when useful
4. training / inference path when useful

## What to show

### File paths

When mentioning code locations, prefer repository-relative paths.

Good:

- `network/TEM.py`
- `util/transfer.py`
- `train.py`

Avoid absolute local paths in the article body.

### Code snippets

If code is shown in the note:

- keep snippets selective, not excessive
- prefer the smallest block that supports the explanation
- add Chinese comments or Chinese line-by-line explanation around the snippet
- make the snippet readable even if the original repository has little or no comments

Do not paste a large raw code block without explanation.

### Chinese annotation requirement

When displaying code, make sure the reader can understand it in Chinese.

Two acceptable patterns:

1. add Chinese inline comments into the shown snippet
2. keep the snippet close to original form, but add clear Chinese explanation immediately above or below it

If the code is hard to read without guidance, prefer commented presentation.

## Recommended structure in the note

When code mapping is included, use a pattern like this:

1. state what part of the paper is being mapped
2. give the repository-relative file path
3. explain input/output meaning
4. explain tensor or data flow when useful
5. show a short snippet with Chinese comments or nearby Chinese explanation
6. conclude what this snippet proves about the paper implementation

## Good behavior

Prefer:

- explain one module at a time
- connect code back to equations or figures
- state clearly when the mapping is approximate rather than exact

Avoid:

- generic repository tours
- long raw code dumps
- absolute filesystem paths in the article body
- code paragraphs that do not map back to the paper

Read `code-mapping-example.md` if you need a concrete writing pattern.

## Mini checklist

Before keeping a code section, verify:

- repository-relative path is shown
- the mapping is real
- Chinese explanation is present
- the snippet is necessary
- the snippet supports the surrounding paragraph
