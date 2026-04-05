# Anti-AI Style Guide

Use this file during the second review pass.

## Goal

Make the note read like a careful human-written paper-reading blog post, not a generic AI summary.

## Remove these patterns

### Empty evaluation

Avoid phrases like:

- 这篇论文非常有意思
- 该方法十分巧妙
- 作者做了大量实验
- 取得了显著效果

Unless the next sentence explains exactly why, delete them.

### Generic transitions

Avoid repetitive transitions like:

- 首先
- 其次
- 最后
- 总的来说
- 值得注意的是
- 需要指出的是

Use them only when they actually help structure the paragraph.

### Abstract paraphrase disguised as analysis

Do not simply restate the abstract in smoother Chinese.

Instead:

- identify the problem
- explain the mechanism
- connect results back to the mechanism

### Table dumping

Do not write paragraphs that only list metrics.

Bad pattern:

- 在数据集A上是x，在数据集B上是y，在数据集C上是z。

Better pattern:

- 这些结果说明该方法在不同数据集上都保持了稳定优势，尤其是在 xxx 场景下更明显。

### Fake novelty

Do not invent novelty points that the paper cannot support.

If the paper is incremental, write it as incremental.

### Inflated certainty

Do not turn plausible interpretation into absolute fact.

Prefer:

- 这表明
- 这支持了
- 这说明作者想解决的是
- 从结果看，更合理的解释是

Over:

- 这证明了
- 本质就是
- 毫无疑问

## Preferred writing behavior

### Be specific

Prefer:

- 该模块先做通道重标定，再做跨模态交互。

Over:

- 该模块进一步增强了特征表达能力。

### Keep interpretation tied to evidence

For every strong conclusion, ask:

- which formula supports it
- which figure supports it
- which table supports it

If none do, weaken or delete the sentence.

### Stay objective

The note can analyze, but should not sound like promotion or personal fan commentary.

### Keep paragraphs purposeful

Each paragraph should do one main job:

- define a problem
- explain a mechanism
- interpret a result
- state a limitation

If a paragraph does more than one badly, split it.

## Final pass mini-check

- [ ] no empty praise
- [ ] no repeated transitions
- [ ] no abstract-only paraphrase
- [ ] no metric dumping without interpretation
- [ ] no invented novelty
- [ ] no overconfident language without evidence
