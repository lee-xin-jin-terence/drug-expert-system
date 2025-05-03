> **Academic Research Paper – Affective Computing**<br/>
> This report was submitted as part of a university project exploring Affective Computing applications in emergency medical decision support.
> **Author:** Terence Lee

# Expert System for Diagnosing and Advising Treatment for Substance Poisoning

## Introduction

This report describes an expert system called **DrugES** that provides quick diagnosis and treatment advice for suspected substance abuse poisoning patients during pre-hospital emergency care. *Pre-hospital emergency care* refers to the care offered by emergency medical responders before reaching the hospital \[1].

Diagnosing substance abuse poisoning in a pre-hospital setting (e.g., inside an ambulance) can be challenging due to limited medical equipment. However, knowing the type of poisoning can enable life‑saving interventions. For instance:

* **Opioid overdoses** can be reversed if **Naloxone** is administered promptly \[2].
* **CNS stimulant intoxication** (e.g., cocaine) can cause cardiovascular or cerebrovascular failure; **benzodiazepine sedation** may mitigate severe effects \[3].

## Goals of DrugES

1. Provide a diagnosis of suspected substance poisoning.
2. Offer pre-hospital treatment advice based on the diagnosis.
3. Explain its diagnostic reasoning.
4. Maintain a knowledge base of the five most commonly abused substance groups.
5. Be user-friendly.
6. Produce results within two minutes.

## Background Information

### Substance Abuse Statistics

* **England (2019):** >18,000 hospitalisations due to drug misuse (NHS) \[4].
* **USA (2019):** >70,000 overdose‑related deaths (CDC) \[5].
* **Canada (2020):** <br/>\~81,000 hospitalisations from substance abuse (CIHI) \[6].

### Related Work

No expert system currently diagnoses pre-hospital substance poisoning. An oral fluid screening device diagnosed amphetamines but failed on cannabis, cocaine, and opiates—and lacked treatment advice \[7].

## AI Methods and Tools

### A. Rule-Based Forward Chaining

DrugES uses **forward chaining** to infer substance poisoning from user‑entered symptoms \[8]. Medical rules are represented as IF–THEN statements:

**Example Rule**:

```
IF pupils are pinpoint
  AND difficulty breathing
  AND unconscious
THEN opioid overdose → administer Naloxone
```

DrugES logs each inference step to justify its advice.

### B. Knowledge Sources

Rules derive from medical texts:

* *Oxford Handbook of Emergency Medicine* \[9]
* *Poisoning and Toxicology Handbook* \[10]

### C. Implementation: ES-Builder Shell

DrugES is implemented in **ES-Builder**, a web‑based expert system shell \[11]. It supports forward chaining and provides a GUI with simple Yes/No prompts—no scripting required.

## Evaluation Method

### Test 1: Correctness of Diagnosis and Advice

* Validates DrugES against expected outcomes for all symptom combinations.
* **Result:** 16/16 correct (100%).

### Test 2: Efficiency of Diagnosis

* Estimates time per test using typical observation durations (e.g., pupil check = 5s).
* **Result:** 75% within 60s, 25% within 120s; all under 2 minutes.

### Test 3: Usefulness & Usability

* Planned questionnaire for 50 pre-hospital staff (requires ethics approval). Not conducted due to time and COVID‑19 constraints.

## Results

| Test                     | Passed | Failed | Total | Pass Rate |
| ------------------------ | ------ | ------ | ----- | --------- |
| Correctness of diagnosis | 16     | 0      | 16    | 100%      |
| Efficiency (≤120s)       | 16     | 0      | 16    | 100%      |

## Conclusion

DrugES meets most goals: accurate, explainable diagnoses and advice within two minutes for five substance groups. Usability testing remains outstanding. Future work could address:

* **Substance specificity:** Current rules cover general classes (e.g., opioids), not individual drugs.
* **New psychoactive substances (NPS):** NPS effects are poorly understood \[13].

Overall, DrugES successfully demonstrates a rule‑based expert system for pre-hospital poisoning care.

## References

\[1] Wilson MH et al. “Pre-hospital emergency medicine,” *Lancet*, 2015.<br/>
\[2] WHO. “Opioid Overdose.” Accessed 31 May 2021.<br/>
\[3] Riba MB, *Clinical Manual of Emergency Psychiatry*, 2010.<br/>
\[4] NHS Digital. “Statistics on Drug Misuse, England, 2019.”<br/>
\[5] CDC. “Drug Overdose Deaths,” 2021.<br/>
\[6] CIHI. “Hospital visits for substance use increased…,” 2021.<br/>
\[7] Söderqvist M et al. “Substance Abuse Among EMS Patients,” *Point of Care*, 2018.<br/>
\[8] Negnevitsky M, *Artificial Intelligence: A Guide to Intelligent Systems*, 2011.<br/>
\[9] Wyatt JP et al., *Oxford Handbook of Emergency Medicine*, 2020.<br/>
\[10] Leikin JB & Paloucek FP, *Poisoning and Toxicology Handbook*, 2008.<br/>
\[11] ES-Builder Web, McGoo Software. Accessed 31 May 2021.<br/>
\[12] WHO. “Coronavirus.” Accessed 31 May 2021.<br/>
\[13] UNODC. “What are NPS?” Accessed 15 Jul 2021.

## Appendix: DrugES Usefulness and Ease of Use Questionnaire

**For Medics (Pre-hospital Personnel)**

This questionnaire gauges the usefulness and ease of use of DrugES. Please circle the most appropriate answer for each statement.

1. I find DrugES useful and will likely use it if the need arises.

   * Strongly Disagree  |  Disagree  |  Agree  |  Strongly Agree

2. DrugES is likely to make pre-hospital treatment of suspected substance abuse patients more efficient.

   * Strongly Disagree  |  Disagree  |  Agree  |  Strongly Agree

3. The diagnosis and treatment advice provided was sufficiently detailed for my needs as a medic.

   * Strongly Disagree  |  Disagree  |  Agree  |  Strongly Agree

4. The diagnosis and treatment advice provided was delivered quickly enough for my needs as a medic.

   * Strongly Disagree  |  Disagree  |  Agree  |  Strongly Agree

5. DrugES is easy to use and navigate.

   * Strongly Disagree  |  Disagree  |  Agree  |  Strongly Agree

6. I am satisfied with DrugES.

   * Strongly Disagree  |  Disagree  |  Agree  |  Strongly Agree

7. I would recommend DrugES to other medics for use.

   * Strongly Disagree  |  Disagree  |  Agree  |  Strongly Agree

## User Guide

1. Open browser: [http://www.mcgoo.com.au/esbuilder/viewer/viewES.php?es=732ee6cdb5a3afda870fc031627bddb3](http://www.mcgoo.com.au/esbuilder/viewer/viewES.php?es=732ee6cdb5a3afda870fc031627bddb3)
2. Click **Search Expert System**.
3. Answer Yes/No prompts (<2 min).
4. View diagnosis & treatment advice.
5. Administer treatment.
