---
name: paper-notes-skill
description: Generate structured Chinese paper-reading notes from a user-provided academic PDF, optionally with a user-provided code repository or a repository link found in the paper abstract. Use when the task is to read a paper, understand its method and experiments, map key formulas and workflow diagrams to code when worthwhile, capture method figures/tables/necessary visualizations, and produce a blog-ready markdown note in the user's fixed template. Prioritize direct PDF input; arXiv PDFs may be downloaded directly, but do not rely on generic publisher pages because anti-bot protections are common. Also use when refining such notes through staged drafting, merge, and multi-round acceptance checks for style, screenshots, and anti-AI-voice cleanup.
---

# Paper Notes Skill

## Overview

Produce a blog-ready paper-reading note from a paper PDF.

Treat this as a staged writing workflow, not a one-shot generation task. Read the paper, extract figures/tables, optionally analyze code that clearly matches the paper, draft the article in parts, merge the parts, and run at least two acceptance passes before finalizing.

## Default workflow

### Workflow decision

Use this skill when the user wants a paper-reading note that can be published directly as a blog draft.

Default process:

1. Confirm initialization settings
2. Read the PDF and recover missing metadata if needed
3. Decide whether code analysis is worth including
4. Collect figures/tables that will actually support the written analysis
5. Draft the article in parts
6. Merge, normalize wording, and run at least two review passes

### 1. Confirm initialization settings

If settings are not already fixed for the current run, ask the user for all three:

1. Markdown save location
2. Image save method
3. Image save location

Do not silently assume these values, even if a prior blog structure exists.

### 2. Choose inputs

Use these priorities:

1. User-provided PDF is the primary input
2. If the user also gives a paper webpage, still treat the PDF as primary
3. If the user gives only a title, do not auto-search for the PDF
4. If the user gives an arXiv page, downloading the PDF is acceptable
5. A repository link is optional, not required

If the user provides a repository link, prefer it over links discovered inside the paper.

If multiple repository links somehow appear, ask the user which one to use.

### 3. Read the paper first, then decide code depth

Default reading focus:

- Title and metadata
- Abstract
- Introduction / motivation
- Overall method framework
- Core modules
- Losses
- Training / inference pipeline
- Main experiments
- SOTA comparison tables
- Ablation tables
- Downstream-task results

Do not default to OCR-heavy assumptions for common IEEE / arXiv / ScienceDirect papers. Prefer text extraction first, then page/figure fallback if needed.

If extraction quality is poor, recover by changing extraction approach, revisiting the original PDF pages, and using figures/tables to repair understanding before continuing.

Read `references/failure-recovery.md` whenever metadata, formulas, screenshots, code mapping, or section quality becomes unreliable.

### 4. Handle code only when it is worth writing about

If there is no repository, continue normally and skip code-related sections.

If there is a repository, do not automatically write a code-mapping section. Write it only when the code clearly matches the paper and the mapping adds real value.

Default code-analysis lens:

1. Align the paper's overall workflow diagram with the code
2. Align key formulas with implementation
3. Explain the corresponding code path, tensor shape changes, and forward flow when useful
4. Add training/inference flow only when it materially helps the note

Read `references/code-mapping-guidelines.md` before writing any code-analysis section.

Do not begin with a generic repository tour.
Do not default to running or debugging code.
If runtime verification is truly needed, ask the user first.

Clone repositories only into a temporary location. Clean them up after the code-analysis workflow ends.

### 5. Draft the note in parts

Never ask the model to write the whole article in one shot.

Use staged generation such as:

1. `01-03` 论文信息 / 主要贡献 / 创新点
2. `04 方法`
3. `05 实验分析`
4. Merge and unify wording

Follow `references/staged-workflow.md` as the default execution sequence.

Keep the final article medium-length by default. Do not compress method/expression quality just to be short.

### 6. Write each section with a fixed purpose

#### `01 论文信息`

Include only reliable metadata gathered from the PDF first. When a field is unclear, prefer omission or cautious recovery over guessing.

Typical contents:

- paper title
- authors
- affiliations
- venue / journal
- DOI if clearly available
- code link if clearly available

#### `02 论文主要贡献`

Summarize what the whole work accomplished and why it matters.

Do not turn this section into a bullet-only copy of the abstract. Reconstruct the contribution in readable Chinese based on the paper's full context.

#### `03 论文创新点`

Prefer the paper's own claimed innovations / contributions.

If the paper's novelty claims are weak or repetitive, rewrite them more clearly, but do not invent unrelated novelty points.

#### `04 方法`

This is the core of the note.

Write it in detail. Explain:

- problem framing
- overall pipeline
- core modules
- key formulas
- losses
- training / inference flow when useful
- code mapping when valuable

If code mapping is included, show repository-relative file paths and make sure displayed code has Chinese explanation or Chinese comments.

Do not over-split headings just to look formal. Keep enough structure to make the method readable.

#### `05 实验分析`

Default priority:

1. SOTA comparison tables
2. Ablation tables
3. Downstream-task results

Other items such as visualizations, complexity, generalization, or failure cases are optional unless they materially strengthen the analysis.

The goal is not to repeat the table values mechanically. Explain what the results support.

#### `06 个人声明`

Keep the user's fixed disclaimer wording.

## Output requirements

### Fixed article structure

The final note must follow this structure:

- `## 01 论文信息`
- `## 02 论文主要贡献`
- `## 03 论文创新点`
- `## 04 方法`
- `## 05 实验分析`
- `## 06 个人声明`

Use the user's exact section names and numbering style.

Method content must be written in detail, but heading depth does not need to be split excessively just for appearance. Prefer clear content over over-nested numbering.

### Writing style

Write in Chinese.

Keep the tone objective and restrained. Analyze clearly, but do not turn the note into a strong personal-opinion piece.

For `论文创新点`, prefer the paper's own claimed innovations / contributions instead of inventing a different novelty list.

For `论文主要贡献`, summarize what the whole work accomplished and why it matters.

### Formula handling

Keep all formulas by default.

Match formula numbering to the paper's original tag numbering whenever possible.

### Markdown and image syntax

Use Typora-compatible Markdown.

For images and tables inserted into the article, use captioned markdown links in this form:

`[题注](相对路径)`

Do not use arbitrary inline styles.

Read `references/image-table-guidelines.md` before selecting, cropping, naming, or placing figures and tables.

### Slug and file naming

When following the user's current blog convention, default slug style is:

`paper-venue-year-method-name`

Keep the markdown filename aligned with the slug unless the user overrides it.

Read `references/article-template.md` before drafting. Use it as the exact output skeleton.

## Image and table selection

By default, save and insert:

- Method figures
- Key result tables
- Necessary visualizations

At minimum, prioritize:

- SOTA comparison tables
- Ablation tables
- Downstream-task result tables

If a figure or table is mentioned in the article body, make sure the screenshot/crop actually supports that paragraph.

## Acceptance workflow

Run at least two acceptance passes before finalizing.

Use `references/review-checklist.md` as the mandatory delivery checklist.

Also use `references/anti-ai-style-guide.md` during the second review pass.

Also run an anti-pattern check before delivery. Remove these if they appear:

- empty praise or emotional filler
- obvious AI-sounding transitions
- repeated explanation of the same point
- screenshots that do not match the paragraph using them
- code-analysis paragraphs that do not truly map back to the paper

### Acceptance pass 1: structure and correctness

Check:

- Required template sections all exist
- Method explanation is complete enough
- SOTA comparison, ablation, and downstream tasks are actually covered when present in the paper
- Formula numbering matches the paper as closely as possible
- Code correspondence truly matches the paper before keeping it
- Captions, table references, and relative image paths are correct

### Acceptance pass 2: article quality

Check:

- Remove obvious AI-sounding phrasing
- Remove repetition, filler, and stiff transitions
- Ensure screenshots are cropped appropriately
- Ensure inserted figures/tables are the right ones, not arbitrary nearby content
- Ensure the final markdown can be published directly as a blog draft

## Use these references while writing

Read all of these before drafting or reviewing the article:

- `references/hard-requirements.md`
- `references/article-template.md`
- `references/staged-workflow.md`
- `references/review-checklist.md`
- `references/image-table-guidelines.md`
- `references/anti-ai-style-guide.md`
- `references/failure-recovery.md`
- `references/code-mapping-guidelines.md`
- `references/code-mapping-example.md`

Use them respectively for:

- hard constraints
- exact output skeleton
- staged generation order
- final acceptance review
- figure/table selection and cropping
- anti-AI-voice cleanup
- fallback and repair rules when the workflow becomes unreliable
- code-to-paper mapping rules
- concrete code-mapping writing example
