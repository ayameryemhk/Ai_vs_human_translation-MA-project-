
# AI vs. Human Translation: A Case Study on Student Perceptions in the English Department at the University of Oran 2

 Master's in Linguistics and Applied Languages (LLA), University of Oran 2 – Mohamed Ben Ahmed, Faculty of Foreign Languages, Department of English · Academic Year 2024–2025

**Authors:** Hadj Abdelkader Aya Meriem & Djebri Nour El Houda
**Supervisor:** Dr. Djekoune Souhila
**Contact:** ayameriem14@gmail.com

---

##  Overview

This repository contains the questionnaire data, cleaning script, and descriptive/thematic
analysis behind a Master's dissertation investigating whether AI-powered translation
tools can replace human translators, based on the perceptions of Master's students in
the English Department at the University of Oran 2.

The study responds to the rapid uptake of neural machine translation tools (Google
Translate, DeepL, ChatGPT) in academic settings, and asks whether growing *usage* of
these tools is matched by growing *trust* in their output. Using a mixed-methods
questionnaire (N = 32), the research finds that AI translation is used almost
universally by the sample, yet is rated only moderately accurate and satisfactory
relative to human translation by pointing toward a model of AI as a complementary tool
rather than a replacement.

---

##  Key Findings

- **Near-universal adoption, moderate trust:** 96.88% (31/32) of respondents had used AI translation tools, but perceived accuracy clustered at a modal/median score of **6/10** (mean 6.75), and satisfaction clustered at a modal/median **3/5** (mean 3.28) 
- **No respondent rated AI accuracy below 4/10**, yet only 3.12% (n = 1) gave the maximum score of 10 , a floor and a ceiling on trust even among consistent users.
- **Usage is supplementary, not exclusive:** 81.25% (26/32) use AI translation only "sometimes" vs. 15.62% (5/32) "always," consistent with AI functioning as an accelerator rather than a final, unsupervised output.
- **Limited direct benchmark against paid human translation:** only 31.25% (10/32) had ever used a professional human translation service, so most comparative judgments reflect classroom/academic exposure rather than professional benchmarking (a noted limitation).
- **Qualitative themes** (coded from the six open-ended items; see `analysis/03_thematic_coding.md`):
  - **A - Speed vs. Contextual Fidelity:** AI preferred mainly for speed/convenience with minimal elaboration; human translation preferred with longer justifications centred on context, emotion, and cultural nuance.
  - **B - Premium Cost vs. Cost-Free Efficiency:** willingness to pay for human translation rises sharply with perceived stakes (official documents, conferences, diplomas); rejected as unnecessary for everyday, low-stakes use.
  - **C - Structural Recommendations:** the dominant critique is that AI translates word-by-word rather than capturing whole-text meaning; suggested fixes cluster around context awareness, idiom handling, and emotional tone.
- **Overall conclusion:** AI should be seen as a support tool, not a replacement; the future of translation likely lies in a human-in-the-loop, collaborative model.

---

##  Research Questions

- **RQ1:** How does AI translation compare to human translation in terms of accuracy, efficiency, and reliability?
- **RQ2:** What are the strengths and limitations of AI translation compared to human translation?
- **RQ3:** How do Master's students in the English Department at the University of Oran 2 perceive AI translation tools?
- **RQ4:** What are the implications of AI translation for the future of professional translation?

---

## Methodology

- **Design:** Mixed-methods case study- a single structured questionnaire (Google Forms) combining closed- and open-ended items.
- **Participants:** N = 32, non-probability convenience sample. 87.50% Master's students (9.38% Licence, 3.12% PhD); 75.00% Linguistics and Applied Languages, 9.38% Literature and Civilization, 15.62% other fields; 87.50% female, 12.50% male; 96.88% aged 20–27; self-reported CEFR split 53.12% C1–C2 / 46.88% B1–B2; 81.25% with no formal translation training or professional experience.
- **Instrument:** 18-item questionnaire (Appendix A of the dissertation) — covering demographics, prior AI/human translation experience, preference and justification, a 1–10 perceived-accuracy scale, a 1–5 satisfaction scale, willingness to pay, and open-ended suggestions/outlook.
- **Analysis:** Descriptive statistics (frequencies, percentages, means) for closed items (`analysis/02_descriptive_stats.py`); manual thematic content analysis for open-ended items (`analysis/03_thematic_coding.md`).
- **No formal pilot test or inferential/significance testing** was conducted — findings are descriptive and interpretive, consistent with the study's exploratory, small-N case-study design (see Limitations, Chapter 3.5).
- **Ethics:** Voluntary participation, informed consent, full anonymity (no identifying data ever collected), secure password-protected storage.

---

##  Repository Structure

```text
.
├── README.md
├── requirements.txt
├── data/
│   ├── raw/
│   │   └── survey_responses_raw.csv         # Unmodified Google Forms export (N=32)
│   ├── processed/
│   │   ├── survey_responses_clean.csv       # Dissertation version: renamed/coded columns
│   │   ├── survey_notebook_clean.csv|xlsx   # Output of Notebook 1 (cleaned)
│   │   └── survey_notebook_coded.csv        # Output of Notebook 2 (coded variables added)
│   └── README.md                            # Full variable dictionary
├── analysis/                                # Scripts behind the dissertation's Chapter 3
│   ├── 01_clean_data.py
│   ├── 02_descriptive_stats.py              # Tables & Figures 3.1-3.11
│   └── 03_thematic_coding.md                # Coding scheme for the 6 open-ended items
├── notebooks/                               # Step-by-step Python data analysis (learning portfolio)
│   ├── 01_data_inspection_and_cleaning.ipynb
│   ├── 02_data_transformation.ipynb
│   └── 03_exploratory_analysis.ipynb
├── results/
│   ├── figures/                             # figure_3_1 ... figure_3_11 (dissertation)
│   ├── tables/                              # table_3_1 ... table_3_11 (dissertation)
│   └── exploration/                         # extra tables and figures from the notebooks
└── docs/
    ├── dissertation.pdf
    └── questionnaire.pdf                    # Appendix A - full instrument
```

### Reproducing the results

```bash
pip install -r requirements.txt
python analysis/02_descriptive_stats.py      # run from the repository root
```

The dissertation scripts in `analysis/` use paths relative to the repository root, so run them from there.

### Python data-analysis notebooks (added after the dissertation)

The three notebooks in `notebooks/` repeat and extend the analysis in a step-by-step, explained way,
starting directly from the raw Google Forms export (`data/raw/survey_responses_raw.csv`).
They are a practical record of the data-analysis skills used on this dataset (Python, Pandas, NumPy, Matplotlib).
They do **not** replace the dissertation's tables, which remain the official results.

| Notebook | Content |
|---|---|
| `01_data_inspection_and_cleaning` | import, inspection, missing values, duplicates, inconsistent answers, renaming, cleaning, filtering, export |
| `02_data_transformation` | coding open-text answers, new columns, NumPy statistics, boolean masks, `groupby`, `crosstab`, `pivot_table` |
| `03_exploratory_analysis` | frequency tables, descriptive statistics, group comparisons, correlations, charts; outputs in `results/exploration/` |

Run them in order with `jupyter notebook` from the `notebooks/` folder.

### Known differences between the script output and the dissertation

- **Table 3.6 (formal training):** the dissertation reports 26 "No / Never" and 6 "Yes / Conditional". The script gives
  27 "No / Never", 3 "Yes / Conditional" and 2 missing answers (R01, R08). The free-text answers do not show which
  respondents the dissertation counted differently, so this table must be checked against the original coding before it is quoted.
- Tables 3.7 to 3.9 previously dropped the "Not very often" answer and the missing answers and recalculated percentages on 30 or 31 people.
  This was caused by a trailing space in `Not very often ` and by the denominator. Both are corrected in `analysis/02_descriptive_stats.py`.

---

##  Limitations

- Small sample (N = 32), single institution — not statistically generalizable.
- Sample skewed heavily female (87.5%) and Master's-level (87.5%); findings should be read as representative of this cohort, not of translation students broadly.
- All accuracy/satisfaction data are self-reported perceptions, not benchmarked against expert-rated or gold-standard translation output.
- Only a single coder performed the thematic analysis of open-ended responses; no inter-rater reliability statistic was computed.


---

##  Select Bibliography

- Bahdanau, D. et al. (2015). Neural Machine Translation by Jointly Learning to Align and Translate.
- Vaswani, A. et al. (2017). Attention Is All You Need.
- Koehn, P. (2020). Neural Machine Translation. Johns Hopkins University.
- Jakobson, R. (1959/2004). On Linguistic Aspects of Translation.
- Newmark, P. *A Textbook of Translation.*
- (Full list in dissertation, Bibliography, pp. 77–78)
ibliography, pp. 77–78)
