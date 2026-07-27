# Data

## Provenance
The data were collected via an anonymous Google Forms questionnaire distributed to
Master's-level students (predominantly Linguistics and Applied Languages) in the
English Department, University of Oran 2, between 16–18 February 2025. N = 32
usable responses. No names, student IDs, or contact details were collected at any
point, consistent with the informed-consent and anonymity procedures described in
Chapter 2.5 of the dissertation.

- `processed/survey_responses_clean.csv` — same data, with columns renamed to
  short codes (see dictionary below) and two derived/coded columns added.

## Variable dictionary

| Column | Type | Description | Corresponds to |
|---|---|---|---|
| `respondent_id` | string | Anonymized ID (R01–R32), assigned by submission order | — |
| `timestamp` | datetime | Google Forms submission timestamp | — |
| `age_group` | categorical | Under 20 / 20–27 / over 27 | Q1 |
| `gender` | categorical | Female / Male | Q2 |
| `education_level` | categorical | Licence / Master / PhD | Q3 |
| `field_of_study` | categorical | Linguistics and Applied Languages / Literature and Civilization / Other Fields | Q4 |
| `profession_free_text` | free text | Self-reported profession (mostly student/teacher) | Q5 |
| `cefr_level` | categorical | B1–B2 / C1–C2 (self-reported) | Q6 |
| `formal_training_free_text` | free text | Raw answer on formal translation training / professional experience | Q7 |
| `formal_training_coded` | categorical (derived) | Recoded to "No / Never" or "Yes / Conditional" — reproduces Table 3.6 | Q7 |
| `ai_tool_ever_used` | categorical | Yes / Not very often | Q8 |
| `ai_use_frequency` | categorical | Sometimes / Always | Q9 |
| `human_service_ever_used` | categorical | Yes / No | Q10 |
| `q11_preference_why` | free text | AI vs. human preference + justification (Theme A) | Q11 |
| `accuracy_score_1_10` | integer | Perceived AI accuracy relative to human translation, 1–10 | Q12 |
| `q13_speed_influence` | free text | Which method is faster / does speed drive preference (Theme A) | Q13 |
| `q14_context_idioms` | free text | How each method handles context/idioms (Theme A) | Q14 |
| `satisfaction_score_1_5` | integer | General satisfaction with AI vs. human translation, 1–5 | Q15 |
| `q16_willing_to_pay_why` | free text | Willingness to pay more for human translation + why (Theme B) | Q16 |
| `q17_suggested_improvements` | free text | Suggested improvements for AI tools (Theme C) | Q17 |
| `q18_future_outlook` | free text | Predicted future of translation / which method dominates | Q18 |

## Reproducing the dissertation's tables/figures

```bash
pip install -r ../requirements.txt
python 01_clean_data.py            # writes data/processed/survey_responses_clean.csv
python 02_descriptive_stats.py     # writes results/tables/*.csv and results/figures/*.png
```

All eleven closed-item frequency tables (3.1–3.11) and their corresponding charts
(Figures 3.1–3.11) from Chapter 3 of the dissertation are reproduced exactly from this
raw file — see `results/tables/` and `results/figures/`.

## Licensing / reuse note
This is primary survey data collected for academic research under the ethical
procedures described in the dissertation (voluntary participation, informed consent,
anonymity). If reusing or redistributing, please retain attribution to the dissertation
and do not attempt to re-identify respondents from free-text answers.
