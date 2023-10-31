# Drug Database Exploration: Health Analytics

**Author:** Masixole Boya

---

## Introduction

### Problem Statement

The objective of this analysis is to gain a deeper insight into the dataset, exploring the described drug attributes. Specifically, we are looking at things like how strong a medicine is, if a doctor needs to prescribe it, how safe it is during pregnancy, how the law sees its use, if it interacts with alcohol, and what people think about it. We also want to see how medicines that could be easily misused might affect public health. Our goal is to give doctors, people who make rules, and others important information about medicines and how they can affect patients.

### Data Dictionary

The dataset has several key attributes that aid in understanding the properties of drugs and their relationships with medical conditions. Here is a brief data dictionary outlining the crucial features:

- **drug_name:** The name of the drug.
- **medical_condition:** The associated medical condition for the drug.
- **activity_percentage:** Activity level of the drug.
- **rx_otc:** Prescription status of the drug (Rx = Prescription Needed, OTC = Over-the-counter).
- **pregnancy_category:** Pregnancy categorization for the drug.
- **csa:** Controlled Substances Act (CSA) schedule for the drug.
- **alcohol:** Interaction of the drug with alcohol.
- **rating:** User rating for the drug (1 = least effective, 10 = most effective).
- **no_of_reviews:** Number of reviews contributing to the rating.
- **drug_link:** Link to additional drug information.
- **medical_condition_description:** Description of the medical condition associated with the drug.
- **medical_condition_url:** URL for further details about the medical condition.

Based on the dataset from Kaggle: [Drugs Related to Medical Conditions](https://www.kaggle.com/datasets/jithinanievarghese/drugs-related-to-common-treatments/)

---

## Exploration

### 1. Basic Preprocessing

#### 1.1) Merge the two datasets

We merged two datasets, one containing medical conditions and the other containing drugs per condition, to create a comprehensive dataset for analysis.

#### 1.2) Activity column: change name to activity_percentage

We renamed the 'activity' column to 'activity_percentage' for clarity and removed the '%' symbol from the values. Additionally, we converted this column to integer type for consistency.

### 2. Basic Data Exploration

#### 2.1) Plot and characterize the distribution of activity_percentage

We visualized the distribution of activity percentages, providing insights into the overall activity level of drugs.

#### 2.2) How many drugs are available for each medical condition?

We determined the number of drugs available for each medical condition, helping us understand the variety of treatments available.

#### 2.3) How many unique drugs are listed in the dataset?

We identified the total number of unique drugs in the dataset, indicating the diversity of drugs included.

### 3. Activity Analysis

#### 3.1) Which drug has the highest activity based on site visitor activity?

We found the drug with the highest activity percentage, potentially indicating its strong effectiveness or popularity.

#### 3.2) Provide a brief interpretation of what this might indicate.

We offered an interpretation of the drug with the highest activity, considering its primary usage and potential medical conditions.

### 4. Prescription Analysis

#### 4.1) How many drugs are available over-the-counter (OTC) vs. prescription (Rx)?

We determined the number of drugs available without a prescription (OTC) and those requiring a prescription (Rx).

#### 4.2) Which medical condition has the highest number of OTC drugs?

We identified the medical condition with the highest number of over-the-counter drugs, providing insights into treatment accessibility.

### 5. Pregnancy Category Analysis

#### 5.1) List the number of drugs in each pregnancy category.

We listed the number of drugs in each pregnancy category, offering an overview of pregnancy-related drug classifications.

#### 5.2) Which medical condition has the highest number of drugs in category X?

We identified the medical condition with the highest number of drugs in category X, potentially indicating areas of specific concern during pregnancy.

#### 5.3) What might be the implications for pregnant women with this condition?

We discussed the potential implications for pregnant women with specific medical conditions, considering the associated category X drugs.

### 6. Controlled Substances Act (CSA) Schedule Analysis

#### 6.1) How many drugs fall under each CSA schedule?

We determined the number of drugs in each Controlled Substances Act (CSA) schedule, highlighting the legal classifications of drugs.

#### 6.2) Identify drugs that have multiple schedules.

We identified drugs that have multiple CSA schedules, potentially indicating complex compositions.

#### 6.3) Provide a brief interpretation of what this might indicate.

We offered an interpretation of drugs with multiple CSA schedules, explaining their likely diverse therapeutic effects.

---

## Advanced Analysis

### 9.1) Are there any correlations between a drug's rating and its activity based on site visitor activity?

We explored the correlation between a drug's rating and its activity percentage, providing insights into user perceptions.

### 9.2) What might this indicate about user preferences or drug effectiveness?

We discussed the implications of the correlation findings on user preferences and drug effectiveness, highlighting factors that influence user ratings.

### 9.3) For drugs that require a prescription (Rx), how does their average rating compare to those that are available over-the-counter (OTC)?

We compared the average ratings of prescription drugs (Rx) to over-the-counter drugs (OTC), offering insights into user perceptions of these two categories.

---

## Contextual Analysis

### Analyze the potential public health implications of drugs that have a high potential for abuse (CSA schedules 1 and 2). Discuss strategies to mitigate the risks associated with these drugs.

We explored the public health implications of drugs with a high potential for abuse, particularly those classified under CSA schedules 1 and 2. We discussed strategies to mitigate the associated risks and promote responsible usage.

---

## Case Study

### Choose a specific drug from the dataset. Analyze its properties, including its activity, prescription status, pregnancy category, CSA schedule, alcohol interaction, and rating. Provide a comprehensive review of the drug, including potential use cases, risks, and benefits.

We selected a specific drug from the dataset, analyzed its properties, and provided a comprehensive review. This analysis included insights into its activity, prescription status, pregnancy category, CSA schedule, alcohol interaction, rating, and potential use cases, risks, and benefits.

---

## References

- Deer, T.R., Pope, J.E., Hanes, M.C. and McDowell, G.C., 2019. Intrathecal therapy for chronic pain: a review of morphine and ziconotide as first-line options. Pain Medicine, 20(4), pp

