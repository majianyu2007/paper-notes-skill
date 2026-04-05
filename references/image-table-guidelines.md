# Image and Table Guidelines

Use this file when selecting, cropping, naming, and inserting figures or tables.

## Selection priority

Default priority:

1. method figures
2. SOTA comparison tables
3. ablation tables
4. downstream-task tables
5. necessary visualizations only when they support a paragraph directly

Do not collect figures or tables just because they exist.

## What to capture

### Method figures

Capture when the figure helps explain:

- overall pipeline
- module structure
- training / inference flow
- data flow between branches

### Tables

Capture when the table supports:

- main SOTA comparison
- ablation conclusions
- downstream-task conclusions
- complexity comparison only if it is discussed in the article

### Visualizations

Capture only when they prove something used in the text, such as:

- qualitative superiority
- failure mode
- robustness under degradation
- segmentation / detection transfer effect

## Cropping rules

### General

- crop tightly
- keep the whole figure or table readable
- do not cut away titles, row labels, column labels, legends, or key annotations
- do not include large useless margins
- do not mix adjacent unrelated figures into one screenshot unless the paper itself presents them as a single composite figure

### Multi-column PDF handling

- if a figure spans both columns, capture the full figure cleanly
- if a table spans both columns, keep the full table and its header intact
- if a figure is split by the PDF layout, re-crop carefully so the final screenshot looks natural

### Composite figures

- keep all subfigures when the paragraph discusses the full composite evidence
- crop only subparts if the article discusses only one subfigure and the crop remains self-contained

## Caption rules

Insert with this format only:

`[题注](相对路径)`

### Caption content

Good captions should say what the reader is looking at and why it matters.

Preferred structure:

- what the figure/table is
- what it demonstrates in one sentence

Examples:

- `[图3 方法总览。上半部分负责跨域对齐，下半部分负责跨任务桥接。](../images/slug/fig3-overview.png)`
- `[表2 MSRS 上的 SOTA 对比结果。该表主要支撑本文在主指标上的整体优势判断。](../images/slug/table2-sota.png)`

Avoid empty captions such as:

- 图3
- 方法图
- 实验结果

## Naming suggestions

Prefer semantic names over random timestamps when possible.

Recommended patterns:

- `fig1-overview.png`
- `fig2-framework.png`
- `table1-sota.png`
- `table2-ablation.png`
- `fig5-qualitative.png`

If a source filename is messy but stable and renaming is expensive, keep it only if the relative path remains manageable.

## Placement rules

- place the figure or table near the paragraph that analyzes it
- do not stack many screenshots first and explain them later
- every inserted figure/table should be referenced by the surrounding text
- if a paragraph depends on a table, make sure the table appears before or immediately after that paragraph

## Review checks

Before final delivery, verify:

- the crop is readable
- the crop matches the paragraph using it
- the caption is informative
- the relative path is correct
- the screenshot is not blurry or cut off
