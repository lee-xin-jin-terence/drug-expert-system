> **Academic Research Paper – Expert Systems**  <br/>
> This report was submitted as part of a university project exploring Expert Systems applications in pre-hospital emergency medical decision support.  <br/>
> Visit <a href="http://www.mcgoo.com.au/esbuilder/viewer/viewES.php?es=732ee6cdb5a3afda870fc031627bddb3" target="_blank">DrugES</a> to explore the system. <br/>
> **Author:** Terence Lee

# Expert System for Diagnosing and Advising Treatment for Substance Poisoning

## Introduction

This report describes an expert system called **DrugES** that provides quick diagnosis and treatment advice for suspected substance abuse poisoning patients during pre-hospital emergency care. *Pre-hospital emergency care* refers to the care offered to patients by emergency medical responders before reaching the hospital \[1].

It can be challenging to diagnose suspected substance abuse poisoning in a pre-hospital setting (e.g. inside an ambulance) when there is limited access to medical equipment. However, knowledge of the type of substance abuse poisoning can provide valuable life-saving medical treatment for patients.

For example, death from opioid overdose can be avoided if the antidote Naloxone is administered on time \[2]. Central nervous system (CNS) stimulant intoxication from drugs such as cocaine can be fatal in severe cases, usually from cardiovascular or cerebrovascular causes. Pre-hospital treatments, such as sedation using benzodiazepines (BZDs), can provide some degree of safeguard against the harmful effects of CNS stimulants \[3].

## Goals of DrugES

1. Provide a diagnosis of suspected substance poisoning.
2. Offer pre-hospital treatment advice based on the diagnosis.
3. Explain its diagnostic reasoning.
4. Maintain a knowledge base of the five most commonly abused substance groups.
5. Be user-friendly.
6. Produce results within two minutes.

## Background Information

### A. Substance Abuse Statistics

In 2019, according to the National Health Service (NHS), poisoning by drug misuse accounted for more than 18,000 hospitalisations in England, United Kingdom \[4]. In the same year, more than 70,000 drug overdose-related deaths occurred in the United States \[5]. In addition, the Canadian Institute for Health Information (CIHI) reports that nearly 81,000 Canadians were hospitalised due to substance abuse in 2020 \[6].

### B. Related Works

There have been no similar expert systems developed to provide a pre-hospital diagnosis of suspected substance abuse poisoning. However, there was an attempt to screen for substance abuse in a pre-hospital setting through the use of oral fluid screening equipment \[7]. The equipment was sufficiently accurate in screening for amphetamine-type drugs but failed to detect other classes of drugs such as cannabis, cocaine, and opiates. Moreover, the screening device could only test for the presence of drugs and lacked the provision of important pre-hospital medical advice for treating suspected substance overdose patients.

## AI Methods and Tools

### A. AI Method: Rule-based Forward Chaining

DrugES uses a rule-based forward-chaining approach \[8] to infer the type of substance abuse based on the patient’s symptoms. The medical knowledge base is represented by multiple IF–THEN rules. First, the user inputs the patient’s symptoms. The inference engine then applies the rules to determine the suspected substance poisoning type.

Based on the inferred poisoning, DrugES provides relevant pre-hospital treatment advice. For example:

**RULE 1:**

```
IF pupils are pinpoint
  AND difficulty breathing
  AND unconscious
THEN patient is suffering from an opioid overdose → administer Naloxone
```

DrugES logs each inference step, ensuring that users can trace and understand its reasoning, which builds trust in the system’s advice.

### B. DrugES Knowledge Source

The AI knowledge base is drawn from reputable medical textbooks and toxicology manuals, including:

* *Oxford Handbook of Emergency Medicine* \[9]
* *Poisoning and Toxicology Handbook* \[10]

These sources inform the IF–THEN rules used by DrugES.

### C. Implementation: ES-Builder Shell

DrugES is implemented using **ES-Builder**, a web-based expert system shell \[11]. ES-Builder:

* Requires no installation (accessible via web browser)
* Supports forward-chaining inference
* Features a GUI with simple Yes/No prompts (no scripting needed)

This implementation ensures ease of development and usability for pre-hospital staff.

## Evaluation Method

DrugES is evaluated based on three different tests, but only the first two tests are conducted. The last test cannot be conducted due to the lack of time and prior approval.

### A. Test 1: Testing Correctness of Diagnosis and Treatment Advice

This test is conducted to check whether DrugES gives the expected diagnosis and treatment advice based on a patient's symptoms. This test does not verify the accuracy of the diagnosis and treatment advice but validates that DrugES is working as expected.

Each possible combination of symptoms will be tested and checked against its expected diagnosis and treatment advice. The overall score will be calculated as a percentage of correct diagnoses and treatment advice against the total number of diagnoses and treatment advice.

### B. Test 2: Testing Efficiency of DrugES in Diagnosis

The best way to test for DrugES efficiency is to run a simulated field test where two people will test out DrugES using a medical dummy. One person will be in-charged of directly interacting with DrugES, while the other will be executing actions instructed by DrugES. However, it is impossible to test it in such a manner due to the lack of a partner.

Instead, a time-based estimation is used to estimate the time required to make a particular observation. For example, measuring rectal temperature is estimated to take around 20 seconds, while checking whether the patient's pupils are dilated would take around 5 seconds.

This test would pass when the time taken for each test case takes no more than two minutes. Each test case needs to take no more than two minutes because time is precious in a pre-hospital environment. Therefore, it is crucial to provide a quick diagnosis to ensure that a suspected substance poisoning patient receives speedy pre-hospital treatment before reaching the hospital.

### C. Test 3: Testing Usefulness and Ease of Use

A group of 50 pre-hospital staff from various hospitals would be invited to test out DrugES. A questionnaire would be issued to these staff whether DrugES is sufficiently useful and is easy to use. If at least 45 pre-hospital staff (90%) agree that DrugES is sufficiently useful and easy to use, then DrugES would pass this aspect of the test. Refer to the Appendix for the questionnaire.

However, this test cannot be conducted as it requires prior approval from Murdoch University’s Research Ethics Committee. The tight project schedule and the prevalence of the Covid-19 pandemic \[12] also made it difficult to liaise with hospitals.

## Results

Only the results for the first two testable tests are shown. Test 3 will not be shown here as it cannot be tested, as explained in the previous section.

### A. Test 1: Testing Correctness of Diagnosis and Treatment Advice

Each combination of substance poisoning symptoms input resulted in the expected substance poisoning diagnosis and treatment advice. This test passed. The results are detailed in Table I below.

**TABLE I**
Results for Test 1: Correctness of Diagnosis and Treatment Advice

|                                          | Count | Percentage of Total Count (%) |
| ---------------------------------------- | :---: | :---------------------------: |
| Correct Diagnosis and Treatment Advice   |   16  |              100              |
| Incorrect Diagnosis and Treatment Advice |   0   |               0               |
| **Total**                                |   16  |              100              |

### B. Test 2: Testing Efficiency of DrugES in Diagnosis

The time taken to obtain a diagnosis and treatment advice from DrugES is estimated and calculated. All the test cases passed this test.

According to Table II below, most of the diagnoses take no more than 60 seconds (1 minute), much shorter than the maximum passing time of 120 seconds (2 minutes). Only a quarter of the test cases take more than 60 seconds but still within the maximum passing time of 120 seconds.

This shows that DrugES can provide speedy diagnosis and treatment advice for suspected substance poisoning patients. However, this test may not be entirely accurate as it is just an estimation. For a more accurate test, a simulated field test should be conducted.

**TABLE II**
Results for Test 2: Efficiency of DrugES in Diagnosis

|                                                    | Count | Percentage of Total Count (%) |
| -------------------------------------------------- | :---: | :---------------------------: |
| Within 60 seconds (Pass)                           |   12  |               75              |
| More than 60 seconds but within 120 seconds (Pass) |   4   |               25              |
| More than 120 seconds (Fail)                       |   0   |               0               |
| **Total**                                          |   16  |              100              |

## Conclusion

Most of the goals were reached. DrugES provides diagnoses and treatment advice for five commonly abused substance types. DrugES can provide a quick diagnosis and treatment advice within two minutes based on the test results. It can also explain how it reached a particular diagnosis, which is natively provided by the ES-Builder tool used.

Two goals cannot be confirmed whether they were reached: the usefulness and ease of use of DrugES. These two goals require tests that need the use of questionnaires, which cannot be conducted due to the lack of time and prior approval.

Despite the inability to conduct specific tests, the outcome of the project was expected. Planning, implementation, and testing of DrugES went very smoothly, except for a minor problem.

One problem faced was the nature of substance poisoning, where multiple types of poisonings shared many similar symptoms. This problem was overcome by small but significant differences that allow unique identification of a particular substance poisoning.

For this project, the effects of substance abuse poisoning and its associated treatment are the major learning points of this project.

A shortcoming of DrugES is that DrugES diagnoses are based on general substance groups, such as opioids, CNS stimulants, and cannabinoids instead of specific substances. This is made difficult by the similarity of symptoms as mentioned above across various general substance groups. Fortunately, treatment for substance poisoning in medical textbooks is generally written based on the general substance groups instead of specific substances.

Another shortcoming of DrugES is that it does not cover new psychoactive substances (NPS). NPS are synthetic drugs that imitate a wide range of illegally trafficked drugs while attempting to pose as legal drugs. However, the poisoning effects of NPS are still not fully known and understood \[13]. Perhaps in a follow-up project, NPS can be covered in DrugES.

In conclusion, DrugES has been a successful project. It reached most of its goals.

## References

\[1] M. H. Wilson, K. Habig, C. Wright, A. Hughes, G. Davies, and C. H. Imray, “Pre-hospital emergency medicine,” *The Lancet*, vol. 386, no. 10012, pp. 2526–2534, Dec. 2015.<br/>
\[2] “Opioid Overdose”, World Health Organization. \[Online]. Available: [https://www.who.int/news-room/fact-sheets/detail/opioid-overdose](https://www.who.int/news-room/fact-sheets/detail/opioid-overdose). \[Accessed: 31-May-2021].<br/>
\[3] M. B. Riba, in *Clinical Manual of Emergency Psychiatry*, Washington, DC: American Psychiatric Publishing, Inc., 2010, p. 200.<br/>
\[4] “Statistics on Drug Misuse, England, 2019,” NHS Digital. \[Online]. Available: [https://digital.nhs.uk/data-and-information/publications/statistical/statistics-on-drug-misuse/2019/part-1-hospital-admissions-related-to-drug-misuse](https://digital.nhs.uk/data-and-information/publications/statistical/statistics-on-drug-misuse/2019/part-1-hospital-admissions-related-to-drug-misuse). \[Accessed: 31-May-2021].<br/>
\[5] “Drug Overdose Deaths,” Centers for Disease Control and Prevention, 03-Mar-2021. \[Online]. Available: [https://www.cdc.gov/drugoverdose/data/statedeaths.html](https://www.cdc.gov/drugoverdose/data/statedeaths.html). \[Accessed: 31-May-2021].<br/>
\[6] “Hospital visits for substance use increased during the first months of the pandemic,” CIHI, 06-May-2021. \[Online]. Available: [https://www.cihi.ca/en/hospital-visits-for-substance-use-increased-during-the-first-months-of-the-pandemic](https://www.cihi.ca/en/hospital-visits-for-substance-use-increased-during-the-first-months-of-the-pandemic). \[Accessed: 31-May-2021].<br/>
\[7] M. Söderqvist, J. Virta, and A. Kämäräinen, “Substance Abuse Among Emergency Medical Service Patients,” *Point of Care: The Journal of Near-Patient Testing & Technology*, vol. 17, no. 2, pp. 47–49, 2018.<br/>
\[8] M. Negnevitsky, in *Artificial Intelligence: A Guide to Intelligent Systems*, Essex: Addison-Wesley/Pearson, 2011, pp. 35–38.<br/>
\[9] J. P. Wyatt, R. G. Taylor, K. de Wit, and E. J. Hotton, *Oxford Handbook of Emergency Medicine*, Oxford University Press, 2020.<br/>
\[10] J. B. Leikin and F. P. Paloucek, *Poisoning and Toxicology Handbook*, Boca Raton: CRC Press, 2008.<br/>
\[11] ES-Builder Web - McGoo Software. \[Online]. Available: [https://www.mcgoo.com.au/html/es-builder\_web.php](https://www.mcgoo.com.au/html/es-builder_web.php). \[Accessed: 31-May-2021].<br/>
\[12] “Coronavirus,” World Health Organization. \[Online]. Available: [https://www.who.int/health-topics/coronavirus](https://www.who.int/health-topics/coronavirus). \[Accessed: 31-May-2021].<br/>
\[13] “What are NPS?,” United Nations Office on Drugs and Crime. \[Online]. Available: [https://www.unodc.org/LSS/Page/NPS](https://www.unodc.org/LSS/Page/NPS). \[Accessed: 15-Jul-2021].

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

1. Open browser: <a href="http://www.mcgoo.com.au/esbuilder/viewer/viewES.php?es=732ee6cdb5a3afda870fc031627bddb3" target="_blank">DrugES</a>
2. Click **Search Expert System**.
3. Answer Yes/No prompts (<2 min).
4. View diagnosis & treatment advice.
5. Administer treatment.
