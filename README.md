# Machine-Learning-Modeling
## Predictive Modeling of Treatment Charges Before Hospital Admission.
### Author: Isuru De Zoysa

In the current medical setup, managing healthcare costs is challenging for patients, healthcare providers, and insurance companies worldwide [1]. Effectively predicting inpatient hospital charges has a greater influence on financial planning, healthcare management, and resource allocation. However, inpatient medical payment data is confidential; hence, researchers have valued Payment-to-Charge Ratios (PCRs) for hospitals as estimated payments [3]. The foremost objective of this study is to predict inpatient hospital charges using machine learning approaches. This method benefits patients, insurance companies, and medical facility providers for better customer service [1], [6]. 

In personal financial management, these machine-learning models influence patients’ decision-making process before hospital admission by accurately predicting their expenditure on healthcare services [7], [12]. Also, healthcare providers can accurately plan customer services by predicting hospital charges by incorporating the most influential factors that increase healthcare costs [13].

**Current Challenges**

Several factors contribute to the complexity of hospital expenditure prediction:

**Variable Length of Stay:** Patient hospital stays can vary significantly, affecting total costs in unpredictable ways [19]. Research indicates that length of stay alone can account for up to 40% of cost variation in certain medical conditions.

**Treatment Complexity:** Modern medical care often involves multiple procedures, specialists, and treatment modalities, each adding layers of cost variability [4].

**Patient Heterogeneity:** Individual patient characteristics, including demographics, comorbidities, and social determinants of health, significantly impact treatment costs [4]. Recent studies have shown that demographic factors can influence hospital costs by up to 25%.

**Healthcare Environment:** Rapidly evolving medical technologies, treatment protocols, and pricing structures create a constantly changing cost [12].

**Treatment Complexity:** Modern medical care often involves multiple procedures, specialists, and treatment modalities, each adding layers of cost variability [7].

**STUDY GAP**

While traditional cost prediction methods have relied on simple regression models and basic statistical approaches, these methods often fail to capture the complex, non-linear relationships between patient characteristics, treatment patterns, and ultimate costs, a clear need for more sophisticated prediction models that can:

• Handle large volumes of heterogeneous healthcare data.

• Account for complex interactions between variables.

• Adapt to changing healthcare environments.

• Provide accurate predictions across diverse patient populations.

**OBJECTIVES**

This study aims to develop and validate a machine learning-based approach for predicting inpatient hospital costs with the following specific objectives:

1. *Model Development*: Create a robust machine learning model that incorporates diverse data sources, including:
   
• Patient demographic information.

• Clinical diagnoses and procedures.

• Length of stay estimates.

2. *Prediction Accuracy*: Achieve superior prediction accuracy compared to traditional statistical methods by leveraging advanced machine learning algorithms and feature engineering techniques.

**EXPECTED IMPACT**

Accurate hospital cost prediction models have the potential to improve healthcare delivery systems significantly [19]. Research indicates potential benefits including:

• Improve hospital resource allocation and budgeting.

• Enhance insurance pricing and risk assessment.

• Support better financial planning for healthcare providers.

• Enable more transparent cost communication with patients.

• Facilitate more efficient healthcare delivery systems.

**METHODOLOGY**

The data set used for this study is data from Mission Hospital patients in India. There were 248 data points with 24 features categorizing medical data, personal data, stay-at-hospital data and symptoms data.

| Type of Data  | Features            |
|-------|--------------------------|
| Medical data | Key complaint codes, Past medical history code, Implant (Y/N)|
| Personal data| Age, Gender, BMI, Marital Status, Weight, Height, Marital Status|
| Stay at hospital data| Total Length of Stay, Length of stay-ICU, Length of stay- Ward, Mode of arrival, State at arrival, Type of admission, **Total cost**, Cost of implant|
| Symptoms (Diagnostic) data| HR Pulse, BP-High, BP-Low, RR, HB, Urea, Creatinine |

<div align="center"><b>Table 1: Selected Variables.</b></div>



<div align="center">

![Machine-Learning-Modeling](images/Picture1.png)

*Figure 1: Methodology Flowchart.*

</div>

**MODEL EXPERIMENTS**

*RANDOM FOREST*

<div align="center">

![Machine-Learning-Modeling](images/Picture2.png)

*Figure 2: Methodology of Random Forest.*

</div>

*KNN*

<div align="center">

![Machine-Learning-Modeling](images/Picture3.png)

*Figure 3: Methodology of KNN.*

</div>

*GRADIENT BOOSTING*

<div align="center">

![Machine-Learning-Modeling](images/Picture4.png)

*Figure 4: Methodology of Gradient Boosting.*

</div>

*eXTREME GRADIENT BOOSTING*

<div align="center">

![Machine-Learning-Modeling](images/Picture5.png)

*Figure 5: Methodology of eXtreme Gradient Boosting.*

</div>

**MODEL SUITABILITY**

Not all machine learning models are appropriate for predicting hospital charges. In this study, the following models are used for the following reasons.

*RANDOM FOREST MODEL*

1. Handling Nonlinear Relationships: Random forests can capture complex nonlinear patterns through their tree-based structure, where each node split can model different aspects of non-linear relationships. Unlike linear models, they don’t assume a straight line relationship between variables [2].

2. Robustness to Outliers: The bootstrap sampling (bagging) process and the way trees are constructed make random forests naturally resistant to outliers. Each tree only sees a subset of the data, and the averaging of predictions helps minimize the impact of extreme values[16].

3. High Prediction Accuracy: In healthcare cost prediction, Gradient Boosting consistently shows superior performance due to its ability to learn from residuals and capture subtle patterns in the data.[9]
   
4. Automatic Feature Selection: Random forests provide built-in feature importance measures through metrics like Mean Decrease Impurity (MDI) or Mean Decrease Accuracy (MDA), helping identify the most relevant predictors[18].
   
5. Automatic Feature Selection: The ensemble nature of random forests, combining multiple decision trees through bagging and random feature selection, typically leads to strong predictive performance, especially with complex data patterns[8].
   
6. Handling Multicollinearity: Random forests are less affected by correlations between predictors than linear models, as they can use different correlated features in other trees and maintain good prediction accuracy[6].
   
*GRADIENT BOOSTING*

1. Handling Complex Relationships: Gradient Boosting proficients at modelling nonlinear relationships between healthcare costs and various factors (age, comorbidities, treatments, etc.) through its iterative tree-building process. Each tree can capture different aspects of these complex interactions[3].

2. Speed and Performance: TXGBoost achieves faster training speeds through Parallel processing capabilities, Cache optimization, and Out-of-core computing for large datasets, "Weighted quantile sketch" for efficient feature value proposals[21].
   
3. High Prediction Accuracy: In healthcare cost prediction, Gradient Boosting consistently shows superior performance due to its ability to learn from residuals and capture subtle patterns in the data[13]

4. Ability to Handle Mixed Data Types: Healthcare data includes various types (numerical lab values, categorical diagnoses, ordinal severity scores). Gradient Boosting can naturally handle this mix through its tree-based architecture[5].

5. Missing Data Tolerance: TModern Gradient Boosting implementations have built-in strategies for handling missing values, which is crucial in healthcare data where complete records are rare [20].
   
*eXTREME GRADIENT BOOSTING*

1. System Optimization Features: XGBoost implements various memory optimization techniques like "block structure" to handle data storage. These features help manage large-scale healthcare datasets efficiently.
   
2. Speed and Performance: XGBoost achieves faster training speeds through Parallel processing capabilities, Cache optimization, and Out-of-core computing for large datasets, "Weighted quantile sketch" for efficient feature value proposals[15].
   
3. Regularization Capabilities: XGBoost provides comprehensive regularization options: L1 regularization to handle sparsity, L2 regularization to prevent overfitting, Tree pruning based on the loss function, Shrinkage and column subsampling[10].
   
4. Handling Imbalanced Data: XGBoost offers built-in support for imbalanced datasets through the scale_pos_weight parameter, Custom evaluation metrics, Sample weights, and built-in support for various evaluation metrics suitable for imbalanced data[1]

 **IMPORTANT RESULTS**

 | Features  | Categories(Percentages)|
|-------|--------------------------|
| Age| Male (67%), Female (33%)|
| Marital Status| Age, Gender, Unmarried (56%), Married (44%)|
| Type of Admission| Elective (87%), Emergency (13%)|
| Mode of Arrival| Walked in (86%), Ambulance (12%), Transferred (2%) |
| State at the Time of Arrival| Alert (~100%), Confused ( ~0%)  |

Table 2: Categorical Features.

When considering personal data, there are more male patients than female patients, while most are unmarried. Also, when considering stay-at-hospital data, there is more usual admission than emergency admission, while fewer patients use ambulances than walking as their mode of arrival. However, almost all patients were alert when they arrived.

Age is an important factor when predicting the cost,


