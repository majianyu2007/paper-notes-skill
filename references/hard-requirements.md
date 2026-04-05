# Hard Requirements

Use this file as the execution checklist for paper-note generation.

## Input rules

- Primary input is a user-provided PDF.
- If the user also provides a webpage, still prioritize the PDF.
- Do not auto-search for a PDF when the user gives only a paper title.
- arXiv PDF download is acceptable.
- Generic publisher links may have anti-bot protection; do not rely on them.
- Repository link is optional.
- If the user provided a repository link, prefer it.
- If multiple repository links appear, ask the user.

## Repository handling

- Clone only into a temporary directory.
- Clean up after analysis.
- Do not default to running or debugging the code.
- Ask before runtime validation if it is truly needed.
- Skip code-analysis writing entirely when the repository does not add real value.

## Code-analysis default focus

Write code-analysis content only when the repository clearly matches the paper and helps the note.

Default focus order:

1. Paper workflow diagram ↔ code path
2. Key formulas ↔ implementation
3. Tensor shapes / forward flow when useful
4. Training / inference flow when useful

Do not default to generic repository structure tours.

## Writing template

The final article must keep this structure:

- `## 01 论文信息`
- `## 02 论文主要贡献`
- `## 03 论文创新点`
- `## 04 方法`
- `## 05 实验分析`
- `## 06 个人声明`

Use `article-template.md` as the exact starting skeleton.

## Style rules

- Write in Chinese.
- Keep tone objective.
- `论文创新点` should follow the paper's own claimed innovations whenever possible.
- `论文主要贡献` should summarize the whole work.
- Method section must be detailed, but heading depth does not need to be forced too deep.
- Default final length is medium.
- The final article must be directly publishable as a blog draft.

## Formula rules

- Keep all formulas by default.
- Preserve the paper's original equation tag numbering whenever possible.

## Markdown and image rules

- Use Typora-compatible Markdown.
- Insert images/tables with captioned markdown links:
  - `[题注](相对路径)`
- Default image scope:
  - method figures
  - key result tables
  - necessary visualizations
- Minimum priority tables:
  - SOTA comparison tables
  - ablation tables
  - downstream-task tables

## Current blog conventions

- Slug pattern: `paper-venue-year-method-name`
- Images commonly live under `../images/<slug>/...`

Even so, initialization should still ask the user for:

1. Markdown save location
2. Image save method
3. Image save location

## Drafting workflow

Do not generate the whole article in one shot.

Recommended staged drafting:

1. `01-03`
2. `04 方法`
3. `05 实验分析`
4. Merge and unify wording

See `staged-workflow.md` for the operational order and stage-by-stage checks.

## Acceptance workflow

Run at least two review passes.

### Pass 1: structure and content

Check:

- Required template sections exist
- Method explanation is complete
- SOTA comparison, ablation, and downstream tasks are covered when present
- Formula tags are correct
- Code correspondence is genuine
- Captions and relative paths are correct

### Pass 2: final quality

Check:

- Remove AI-sounding phrasing
- Remove repetition and filler
- Check screenshot crops
- Check that selected figures/tables truly match the discussed paragraph
- Confirm blog-readiness

See `review-checklist.md` for the explicit delivery checklist.

## Anti-patterns

Avoid these by default:

- generic repository walkthroughs that do not map back to the paper
- one-shot full article generation
- loose paraphrase of the abstract instead of section-specific writing
- invented innovation points not grounded in the paper
- table-value dumping without interpretation
