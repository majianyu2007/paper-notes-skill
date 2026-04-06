# Review Checklist

Run this checklist before final delivery.

## Pass 1: structure and correctness

### Template

- [ ] blog frontmatter exists
- [ ] `[TOC]` exists
- [ ] `01 论文信息` exists
- [ ] `02 论文主要贡献` exists
- [ ] `03 论文创新点` exists
- [ ] `04 方法` exists
- [ ] `05 实验分析` exists
- [ ] `06 个人声明` exists

### Metadata

- [ ] title is correct
- [ ] authors are correct
- [ ] affiliations are correct when included
- [ ] venue / journal is correct
- [ ] code link is correct or omitted cleanly

### Method

- [ ] overall pipeline is explained
- [ ] core modules are explained
- [ ] all important formulas are retained
- [ ] equation tags follow the paper
- [ ] losses are covered when relevant
- [ ] key judgments are used when they improve analytical clarity
- [ ] code mapping only appears when it truly matches the paper
- [ ] light/heavy code mode is chosen appropriately
- [ ] repository-relative paths are used when code files are shown
- [ ] displayed code has Chinese comments or nearby Chinese explanation
- [ ] code section ends with an evidence-based judgment when appropriate

### Experiments

- [ ] SOTA comparison is covered when present
- [ ] ablation is covered when present
- [ ] downstream tasks are covered when present
- [ ] tables are interpreted, not just copied
- [ ] experiment section forms an evidence chain when the paper supports it

### Images and tables

- [ ] method figures are correctly selected
- [ ] key tables are inserted
- [ ] necessary visualizations are inserted when discussed
- [ ] captions are accurate
- [ ] relative paths are correct
- [ ] screenshot crops are tight and readable
- [ ] figure/table handling follows `image-table-guidelines.md`

## Pass 2: publishability and anti-AI-voice

### Language

- [ ] no obvious AI-sounding transitions
- [ ] no empty praise
- [ ] no filler or repeated explanation
- [ ] no stiff or generic summary language
- [ ] tone remains objective
- [ ] anti-AI cleanup follows `anti-ai-style-guide.md`

### Readability

- [ ] section flow is natural
- [ ] terminology is consistent
- [ ] paragraphs are not bloated
- [ ] medium final length is maintained unless the user asked otherwise
- [ ] section lengths are proportionate and follow `section-length-guidelines.md`

### Blog readiness

- [ ] Typora-compatible Markdown
- [ ] frontmatter fields are complete enough for the blog draft
- [ ] slug/file naming follows the chosen convention
- [ ] images/tables support the written discussion
- [ ] final article can be published directly
- [ ] any unresolved uncertainty has been reduced to conservative wording or removed
