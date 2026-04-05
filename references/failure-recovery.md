# Failure Recovery

Use this file when something in the paper-note workflow becomes unreliable.

## Goal

Do not force a brittle one-pass result. When extraction, evidence gathering, or mapping fails, repair the workflow and continue with the strongest reliable evidence available.

## Failure cases and fallback actions

### 1. PDF text extraction is messy

Symptoms:

- broken reading order
- split equations
- duplicated columns
- unreadable symbols

Fallback order:

1. try another extraction route
2. re-read the original PDF pages directly
3. rely on figures, tables, and captions to repair understanding
4. keep writing only after the core method and experiments are recoverable

Do not pretend the extracted text is trustworthy when it clearly is not.

### 2. Metadata is incomplete

Symptoms:

- missing DOI
- affiliations unclear
- code link unclear

Fallback order:

1. trust the PDF first
2. use the paper webpage only as auxiliary metadata recovery
3. omit uncertain fields rather than guess

### 3. Formula extraction is incomplete

Symptoms:

- equation bodies missing
- numbering present but expressions broken
- symbols corrupted

Fallback order:

1. re-read the PDF page containing the equation
2. manually reconstruct only if the PDF view is clear
3. if a formula is still unreliable, do not invent it
4. explain the mechanism in prose and keep only reliable equations

Equation numbering should still follow the paper for all equations that are retained.

### 4. Method is too complex to explain in one pass

Symptoms:

- many modules with nested dependencies
- multi-stage training
- multiple branches and losses

Fallback order:

1. restate the overall pipeline first
2. split the method into module-level chunks
3. explain each chunk separately
4. merge only after each chunk is individually understandable

Do not collapse the whole method into a vague abstract-style paragraph.

### 5. Code and paper do not align cleanly

Symptoms:

- repository is incomplete
- code names differ heavily from the paper
- no obvious module/formula mapping
- repository looks like a generalized toolbox rather than the paper implementation
- multiple papers seem to share the same repository

Fallback order:

1. search only for direct evidence of mapping
2. keep only the repository parts that map directly to this paper's modules, formulas, or training/inference path
3. if mapping remains weak, omit code-analysis writing
4. continue with the paper note itself

Do not force code paragraphs that cannot be justified.
Do not write a generic toolbox walkthrough just because a repository exists.

### 6. Figures or tables are hard to crop cleanly

Symptoms:

- multi-column layout interference
- low-resolution PDF rendering
- legends or headers get cut off

Fallback order:

1. recrop from the original page view
2. capture the full self-contained figure/table instead of an over-tight crop
3. if a crop remains poor, prefer omitting it over inserting a confusing screenshot

A bad screenshot is worse than no screenshot.

### 7. Experiment section becomes metric dumping

Symptoms:

- paragraphs only list numbers
- no interpretation of what the results support
- table inserted but unused

Fallback order:

1. group results by claim: SOTA / ablation / downstream
2. write the claim first
3. use the table values only to support that claim
4. delete stray numbers that do not support an argument

### 8. The draft sounds too much like AI

Symptoms:

- repetitive transitions
- empty praise
- abstract paraphrase repeated across sections
- generic conclusion language

Fallback order:

1. run the anti-AI style guide
2. shorten or delete filler sentences
3. replace generic praise with evidence-based statements
4. split bloated paragraphs into single-purpose paragraphs

### 9. The final article is too long

Symptoms:

- repeated explanation of the same module
- too many secondary tables or visualizations
- deep code details that add little value

Fallback order:

1. keep the template structure unchanged
2. compress repeated explanation
3. keep method depth but trim low-value repetition
4. keep key tables and remove marginal inserts

## Final rule

When in doubt, prefer:

- reliable over complete
- clear over exhaustive
- justified over speculative
