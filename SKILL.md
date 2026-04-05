---
name: paper-notes-skill
description: Generate structured Chinese paper-reading notes from a user-provided academic PDF, optionally with a user-provided code repository or a repository link found in the paper abstract. Use when the task is to read a paper, understand its method and experiments, map key formulas and workflow diagrams to code when worthwhile, capture method figures/tables/necessary visualizations, and produce a blog-ready markdown note in the user's fixed template. Prioritize direct PDF input; arXiv PDFs may be downloaded directly, but do not rely on generic publisher pages because anti-bot protections are common. Also use when refining such notes through staged drafting, merge, and multi-round acceptance checks for style, screenshots, and anti-AI-voice cleanup.
---

# Paper Notes Skill

## Overview

Produce a blog-ready paper-reading note from a paper PDF.

Treat this as a staged writing workflow, not a one-shot generation task. Read the paper, extract figures/tables, optionally analyze code that clearly matches the paper, draft the article in parts, merge the parts, and run at least two acceptance passes before finalizing.

## Default workflow

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

### 4. Handle code only when it is worth writing about

If there is no repository, continue normally and skip code-related sections.

If there is a repository, do not automatically write a code-mapping section. Write it only when the code clearly matches the paper and the mapping adds real value.

Default code-analysis lens:

1. Align the paper's overall workflow diagram with the code
2. Align key formulas with implementation
3. Explain the corresponding code path, tensor shape changes, and forward flow when useful
4. Add training/inference flow only when it materially helps the note

Do not begin with a generic repository tour.
Do not default to running or debugging code.
If runtime verification is truly needed, ask the user first.

Clone repositories only into a temporary location. Clean them up after the code-analysis workflow ends.

### 5. Draft the note in parts

Never ask the model to write the whole article in one shot.

Use staged generation such as:

1. Paper info + main contributions + innovations
2. Method section
3. Experiment analysis
4. Merge and unify wording

Keep the final article medium-length by default. Do not compress method/expression quality just to be short.

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

### Slug and file naming

When following the user's current blog convention, default slug style is:

`paper-venue-year-method-name`

Keep the markdown filename aligned with the slug unless the user overrides it.

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

## Use this reference while writing

Read `references/hard-requirements.md` before drafting or reviewing the article. It contains the user-confirmed workflow constraints and acceptance checklist for this skill.
