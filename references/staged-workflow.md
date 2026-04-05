# Staged Workflow

Use this as the operational sequence for generating a paper note.

## Stage 0: initialize

Ask the user for:

1. Markdown save location
2. Image save method
3. Image save location

Do not skip this step.

## Stage 1: read and gather evidence

### Input priority

- PDF first
- arXiv PDF allowed
- webpage only as auxiliary
- repository optional

### Read these parts first

1. title / metadata
2. abstract
3. introduction / motivation
4. overall method section
5. main experiments
6. conclusion if needed

### Collect evidence while reading

Keep a running list of:

- reliable metadata
- all equation tags used in the paper
- method figures worth inserting
- SOTA tables
- ablation tables
- downstream-task tables
- optional visualizations that truly support analysis

If text extraction is weak, repair understanding by revisiting PDF pages and figure/table regions.

## Stage 2: decide code-analysis scope

Only continue if the repository clearly maps back to the paper and adds value.

When continuing, focus on:

1. workflow diagram ↔ code path
2. key formulas ↔ implementation
3. tensor shapes / forward path when useful
4. training / inference path when useful

Skip generic repository descriptions.

## Stage 3: draft part A

Draft these sections first:

- `01 论文信息`
- `02 论文主要贡献`
- `03 论文创新点`

Checks before moving on:

- metadata came from the PDF first
- contributions are not just a paraphrased abstract
- innovation points are grounded in the paper

## Stage 4: draft part B

Draft `04 方法`.

Recommended internal order:

1. problem framing
2. overall pipeline
3. core modules
4. formulas
5. losses
6. code mapping if valuable
7. training / inference path if valuable

Checks before moving on:

- formulas are preserved
- equation numbering follows the paper
- method figures are inserted where discussed
- code paragraphs actually map back to the paper

## Stage 5: draft part C

Draft `05 实验分析`.

Default order:

1. SOTA comparison
2. ablation analysis
3. downstream tasks
4. optional extras if they materially help

Checks before moving on:

- not dumping table numbers mechanically
- each major table has interpretation
- key tables are inserted with captions and correct relative paths

## Stage 6: merge

Merge parts A/B/C into the fixed template.

During merge:

- unify terminology
- remove repeated explanations
- normalize heading style
- keep medium final length

## Stage 7: review pass 1

Review structure and factual correctness.

Minimum checks:

- template sections complete
- formulas complete and correctly tagged
- figures/tables match the paragraphs using them
- code-analysis claims are justified

## Stage 8: review pass 2

Review writing quality and publishability.

Minimum checks:

- remove AI-sounding transitions
- remove filler and repetition
- verify screenshot crops
- verify Typora-compatible markdown
- verify the article reads like a blog-ready draft

## Stage 9: final output

Only output the final markdown after both review passes are complete.
