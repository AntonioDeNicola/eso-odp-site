# Keyword Sets and Expert Annotation Resources

## Description

This page provides the keyword-frequency data and expert annotation results used in the development of the Energy System Ontology (ESO). These resources are released to improve the transparency and reproducibility of the keyword selection, semantic categorization, inter-rater agreement analysis, and disagreement-resolution procedure described in the manuscript.

The released material includes the complete keyword-frequency list extracted before expert screening and the workbook containing the individual annotations of six experts across five energy-system categories. Together, the files make it possible to reconstruct the frequency filter, inspect the original expert judgments, reproduce the agreement statistics, and test alternative filtering or voting rules.

---

## Available Files

### Complete keyword-frequency list

📄 [Download `all_topics.txt`](./all_topics.txt)

This UTF-8 text file contains the complete set of **58,226 extracted keywords** and their observed frequencies before expert annotation. Each line uses the following semicolon-separated structure:

```text
keyword;frequency
```

Example:

```text
renewable electricity;117
hydraulic fracturing;18
acid rain;2
```

The file can be used to:

- reconstruct the initial keyword population;
- reproduce the frequency-based selection;
- inspect the long-tail frequency distribution;
- repeat the analysis with alternative minimum-frequency thresholds;
- evaluate the sensitivity of the resulting keyword set to the selected threshold.

### Expert annotation workbook

📊 [Download `Lexicon_data.xlsx`](./Lexicon_data.xlsx)

This workbook contains the annotations assigned independently by **six experts** to **4,581 keywords**. Each keyword was evaluated against five categories representing the principal ESO subsystems:

- Environment;
- Strategy;
- Policy;
- Behavior;
- Operations.

The annotation matrices use binary values:

- `1` — the expert assigned the keyword to the category;
- `0` — the expert did not assign the keyword to the category.

The workbook contains the following worksheets:

| Worksheet | Content |
|---|---|
| `Matrix_Environment` | Individual expert annotations for the Environment category |
| `Matrix_Strategy` | Individual expert annotations for the Strategy category |
| `Matrix_Policy` | Individual expert annotations for the Policy category |
| `Matrix_Behavior` | Individual expert annotations for the Behavior category |
| `Matrix_Operations` | Individual expert annotations for the Operations category |
| `Agreement_per_keyword` | Category-level and mean agreement values for every keyword, including items flagged for review |
| `Fleiss_Kappa` | Fleiss’ kappa values and qualitative interpretations by category and overall |
| `Statistics` | Summary statistics for the annotation exercise |

---

## Frequency Filter

Keywords occurring at least **seven times** were retained for expert annotation. Applying a minimum-frequency threshold of 7 to the complete list produces **4,582 candidate keywords**, compared with 58,226 keywords in the unfiltered list. The released annotation workbook contains 4,581 annotated keywords after preparation of the expert-review set.

The threshold was selected to reduce the large number of rare, highly specific, or noisy terms while retaining a sufficiently broad vocabulary for expert assessment. It reduced the manual annotation burden to a feasible scale without limiting the candidate set to only the most frequent and generic energy terms.

Because the complete frequency list is provided, sensitivity can be assessed by applying alternative thresholds. For reference, the numbers of keywords retained at several nearby thresholds are:

| Minimum frequency | Retained keywords |
|---:|---:|
| 5 | 6,418 |
| 6 | 5,369 |
| **7** | **4,582** |
| 8 | 3,962 |
| 9 | 3,521 |
| 10 | 3,153 |

This table shows the expected trade-off: lower thresholds increase lexical coverage and expert-review workload, whereas higher thresholds produce a smaller and more frequently occurring vocabulary.

---

## Expert Annotation and Majority Voting

Six experts independently assessed whether each keyword belonged to each of the five categories. Disagreements were resolved using a **4 out of 6 majority-voting rule**: a keyword was assigned to a category when at least four experts selected that category.

This rule requires a qualified majority of approximately 66.7%, avoiding acceptance based on a simple 3–3 split while still allowing a category assignment when two experts disagree. Since categories were evaluated independently, a keyword could be assigned to more than one category when it satisfied the majority rule in multiple annotation matrices.

The individual binary judgments are retained in the five `Matrix_*` worksheets, allowing readers to reproduce the majority decisions or apply alternative rules.

---

## Inter-rater Agreement

Inter-rater reliability was evaluated using Fleiss’ kappa. The workbook reports the following values:

| Category | Fleiss’ kappa | Interpretation reported in the workbook |
|---|---:|---|
| Environment | 0.2487 | Fair |
| Strategy | 0.1217 | Slight |
| Policy | -0.0085 | Poor |
| Behavior | 0.0963 | Slight |
| Operations | 0.2388 | Fair |
| **Overall** | **0.1745** | **Slight** |

The `Statistics` worksheet also reports an average agreement value of **0.7805**, a standard deviation of **0.1051**, and **308 keywords** flagged for review because their mean agreement value was below 0.60.

The relatively low kappa values should be interpreted in light of the interdisciplinary nature of the vocabulary and the possibility of assigning keywords to multiple conceptual categories. The release of the complete annotation matrices makes the observed disagreements transparent and supports independent recalculation of agreement measures.

---

## Reuse and Reproducibility

The two files support the following reproducibility tasks:

1. Reconstruct the complete keyword-frequency distribution from `all_topics.txt`.
2. Apply the reported minimum-frequency threshold of 7 or test alternative thresholds.
3. Inspect all six expert judgments for each keyword and category.
4. Reproduce category assignments using the 4 out of 6 majority-voting rule.
5. Recalculate Fleiss’ kappa and keyword-level agreement statistics.
6. Identify and review keywords associated with lower inter-rater agreement.

When reusing these resources, users should preserve the original files and document any normalization, encoding correction, threshold change, or alternative voting rule applied during their analysis.

---

⬅️ [Back to the Home Page](./)
