---
title: Early prediction of Alzheimer's disease
description: >-
  This study explores machine learning methods for early prediction of ADRD using RWD from EHRs. Four computable phenotypes (CPs) identified cases with a 1:10 control match. Logistic regression and gradient boosting tree models were applied across prediction windows of 0, 1, 3, and 5 years. The data-driven model achieved an AUC of 0.854 for 5-year prediction.
author: 
date: 2024-12-24 12:00:00 +0000
categories: [Data Science, Health Research]
tags: [alzheimer's, machine learning, ehr, predictive modeling]
pin: false
mermaid: true
---

### Key Insights

- **Data Source**: EHR data from the OneFlorida+ Research Consortium, covering 23,835 ADRD patients and over 1 million controls.
- **Techniques**: Gradient Boosting Tree (GBT) models outperformed logistic regression, achieving predictive accuracies (AUC) of 0.939 (immediate), 0.906 (1 year), 0.884 (3 years), and 0.854 (5 years before diagnosis).
- **Features**: Models used both knowledge-driven (expert-selected) and data-driven (machine-discovered) features, with data-driven approaches yielding superior results.

### Methodology
#### **Prediction Models**

![Desktop View](/assets/img/ad_prediction_patient_timeline.png){: width="1397" height="211" }
_A patient timeline for the prediction task_

1. **Knowledge-Driven Approach**: Leveraged established ADRD risk factors (e.g., stroke, depression, diabetes).
2. **Data-Driven Approach**: Utilized comprehensive EHR data, identifying novel predictors like mood disorders and preventive care markers.

#### **Performance Metrics**
![Desktop View](/assets/img/ad_prediction_shap_dd_cp3_gpt_5y.png){: width="822" height="766" .w-50 .right}
- Models excelled in identifying high-risk individuals, particularly with shorter prediction windows.
- SHAP (SHapley Additive exPlanations) analysis highlighted key contributing factors, such as age and cerebrovascular disease.

### Practical Implications

- **Clinical Integration**: These models could help identify at-risk patients earlier, enabling timely intervention and personalized care.
- **Research Applications**: Enhanced patient stratification for clinical trials and epidemiological studies.

### Future Directions

To further advance ADRD prediction:
1. **Broader Validation**: Test models with external datasets to ensure generalizability.
2. **Workflow Integration**: Develop clinical tools for seamless use in healthcare settings.
3. **Exploratory Research**: Investigate causal mechanisms behind identified predictors.

## Conclusion

This study highlights the transformative potential of machine learning in healthcare, showcasing how data-driven methodologies can lead to earlier detection and improved outcomes for Alzheimer’s and related dementias. By integrating predictive models into clinical practice, we can take significant steps toward proactive and personalized patient care.

For detailed results and methodology, read the full publication [here](https://alz-journals.onlinelibrary.wiley.com/doi/10.1002/alz.12967).


---
