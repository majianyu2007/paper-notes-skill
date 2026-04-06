# Section Length Guidelines

Use this file to keep each generated part within a controlled size range.

## Goal

Prevent section imbalance.

The note should not have a very short contribution section, an overgrown method section, or an experiment section that turns into uncontrolled metric dumping.

## Default target ranges

These are soft constraints, not rigid quotas.

### Frontmatter + `01 论文信息`

- keep concise
- usually metadata only
- avoid turning this part into prose discussion

### `02 论文主要贡献`

- target: about 300-700 Chinese characters
- enough to explain the paper's real problem and overall contribution
- do not expand into method details too early

### `03 论文创新点`

- target: 3-5 items by default
- each item should usually stay within 1-3 sentences
- avoid writing mini-paragraphs that duplicate `02`

### `04 方法`

- this is usually the longest section
- target: about 1200-3000 Chinese characters for standard papers
- can be longer only when the paper genuinely requires heavy mechanism or code analysis
- if code mapping is heavy, keep the extra detail focused on only the most important modules

### `05 实验分析`

- target: about 600-1500 Chinese characters for standard papers
- enough to cover SOTA, ablation, and downstream evidence chain
- do not let this section become a raw metric transcript

### `06 个人声明`

- fixed text, do not expand

## Stage-level limits

When generating in parts, keep rough control like this:

- Part A (`01-03`): medium-short
- Part B (`04 方法`): longest part
- Part C (`05 实验分析`): medium

A useful practical rule:

- Part B should usually be longer than Part A
- Part C should usually be shorter than Part B but not too thin

## When to compress

Compress if:

- the same point appears in both `02` and `03`
- method paragraphs repeat the same mechanism in different words
- experiment paragraphs list too many numbers without new interpretation
- code mapping explains too many low-value helper functions

## When to expand

Expand if:

- the method logic is still not understandable
- formulas appear without enough explanation
- the evidence chain in experiments is too weak
- a key module is central to the paper's claim but barely explained

## Review rule

Before final delivery, check that section lengths feel proportionate.

If one section is obviously too short or too bloated relative to its role, rewrite before delivering.
