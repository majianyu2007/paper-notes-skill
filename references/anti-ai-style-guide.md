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

### Positive examples for method writing

Bad:

- 作者提出了一个有效的整体框架，用于增强特征表示并提升融合质量。

Better:

- 整体流程分成两步。前一部分负责把红外与可见光特征拉到共享空间，后一部分再利用任务信息反哺融合分支。

Bad:

- 这一模块能够更好地捕获丰富的信息。

Better:

- 这一模块先在通道维度做筛选，再在空间维度做交互，所以它解决的不是单纯的特征增强，而是不同模态之间的信息分配问题。

### Positive examples for experiment writing

Bad:

- 在数据集 A、B、C 上分别取得了 0.91、0.88、0.90 的结果，说明方法有效。

Better:

- 这些结果说明该方法不是只在单一数据集上偶然占优，而是在不同场景下都保持了相对稳定的优势。

Bad:

- 消融实验进一步证明了各模块都很重要。

Better:

- 消融结果表明，性能提升不是由单一模块独立带来，而是来自共享空间对齐和任务反馈两部分的协同作用。

### Positive examples for limitation writing

Bad:

- 该方法仍有一些不足，有待进一步研究。

Better:

- 这篇工作的主要边界在于它默认输入配准较好，因此在更强的视角偏移场景下，当前结果未必能直接成立。

Bad:

- 方法还可以继续优化。

Better:

- 如果后续要继续做这条线，更值得补的不是继续堆模块，而是验证它在更复杂退化条件下是否还能保持同样的优势。

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
