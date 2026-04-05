# Experiment Evidence Chain

Use this file when writing `05 实验分析`.

## Goal

Organize experiments as an evidence chain, not as three disconnected subsections.

The point is to show how the paper supports its main claim step by step.

## Default chain

### 1. 主实验回答 有没有用

This part should answer:

- does the method outperform strong baselines
- on which metrics or datasets is the advantage stable
- what headline claim the main tables support

Do not just list numbers. State what the main evidence supports.

### 2. 消融实验回答 为什么有用

This part should answer:

- which module or mechanism causes the gain
- whether multiple modules are complementary
- whether the method's core story survives ablation

The key is causal interpretation, not metric recitation.

### 3. 下游任务回答 能否迁移

This part should answer:

- whether the fused representation helps segmentation / detection / other downstream tasks
- whether the claimed gain survives outside image-level metrics

This is often the strongest external validation.

## Recommended writing pattern

For each evidence stage, use this order:

1. state the question this stage answers
2. point to the relevant table / figure
3. summarize the result trend
4. say what this result supports

## Suggested headings or transitions

Prefer analysis-oriented phrasing such as:

- 主实验结果真正回答的是……
- 消融实验的意义在于……
- 下游任务验证更关键，因为它说明……
- 这三部分证据合起来支持了……

## Final synthesis

When the paper supports it, add a final paragraph that explicitly ties the chain together:

- main experiment proves effectiveness
- ablation explains mechanism
- downstream task proves transferability

This is often what turns a good note into a strong analytical note.

## Avoid

- treating SOTA / ablation / downstream as three unrelated lists
- repeating table values without interpretation
- letting the experiment section become only metric reporting

## Mini checklist

Before finalizing `05 实验分析`, verify:

- the section has a clear evidence chain
- each major table answers a specific question
- the section ends with a synthesis when appropriate
