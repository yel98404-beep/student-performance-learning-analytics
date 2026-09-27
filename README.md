# Student Performance Prediction: A Learning Analytics Project

## 1. Project Overview

### Research Question
How can students' early academic performance and learning-related characteristics be used to predict their final mathematics grade (G3)?

### Project Purpose
This project examines student performance from a learning analytics perspective using the Student Performance dataset from the UCI Machine Learning Repository. The main purpose is to explore factors associated with students' mathematics performance and to predict their final grade (G3) using earlier academic performance and learning-related characteristics.

In addition to predictive analysis, this project emphasizes clear data documentation and reproducibility. This README provides information about the research question, dataset, files, variables, methodology, data access, metadata standard, and limitations of the analysis.

---

## 2. Researcher Information

- **Author:** Ye
- **ORCID:** [0009-0000-8741-6065](https://orcid.org/0009-0000-8741-6065)
- **Dataset DOI:** [10.24432/C5TG7T](https://doi.org/10.24432/C5TG7T)
- **Dataset Creator:** Paulo Cortez
- **Dataset Source:** UCI Machine Learning Repository

> **Note:** The DOI listed above belongs to the original UCI Student Performance dataset, not to this GitHub project.

---

## 3. Dataset and File Overview

### Data Source

This project uses the **Student Performance** dataset from the UCI Machine Learning Repository. The data describe student achievement in secondary education at two Portuguese schools and were collected through school reports and questionnaires.

The original dataset provides student performance data for two subjects:

- Mathematics (`student-mat.csv`)
- Portuguese language (`student-por.csv`)

This project uses only the **Mathematics dataset (`student-mat.csv`)**.

**Original Dataset:**  
[UCI Student Performance Dataset](https://archive.ics.uci.edu/dataset/320/student+performance)

### Dataset Description

The Mathematics dataset contains **395 observations and 33 variables**. The variables describe students' demographic characteristics, family background, school-related characteristics, study behavior, social characteristics, absences, and academic grades.

The main outcome variable in this project is:

- **G3:** final mathematics grade (0–20)

Two important early academic performance variables are:

- **G1:** first-period grade (0–20)
- **G2:** second-period grade (0–20)

Because G1 and G2 represent performance earlier in the same course, they provide important information for predicting students' final grades.

### File Overview

| File | Description | Format |
|---|---|---|
| `student-mat.csv` | Student performance data for the Mathematics course | CSV |
| `README.md` | Project metadata, data dictionary, methodology, access information, and documentation | Markdown |

---

## 4. Metadata Standard

### Selected Standard: DDI-Codebook

The metadata framework selected for this project is the **Data Documentation Initiative Codebook (DDI-Codebook)**.

DDI-Codebook is designed to support structured documentation of a single research dataset. It can describe information at the study, data file, and variable levels, including the purpose of a study, methodology, data sources, provenance, access information, file structure, and variable definitions.

### Why I Chose DDI-Codebook

I chose DDI-Codebook because this project focuses on a single structured educational dataset. The Student Performance dataset contains many coded variables related to students' demographic, academic, family, and behavioral characteristics, so clear variable-level documentation is especially important.

DDI-Codebook provides a useful framework for organizing information about the study, dataset, files, variables, methodology, and data access. These features make it appropriate for documenting this learning analytics project.

This README does not implement the complete DDI XML schema. Instead, its structure and documentation are informed by the principles and major information categories of DDI-Codebook.

---

## 5. Data Dictionary

The following data dictionary documents the 33 variables contained in `student-mat.csv`.

| Variable | Type | Values / Range | Description |
|---|---|---|---|
| `school` | Categorical | GP, MS | Student's school: Gabriel Pereira (GP) or Mousinho da Silveira (MS) |
| `sex` | Binary | F, M | Student's sex |
| `age` | Integer | 15–22 | Student's age |
| `address` | Binary | U, R | Home address type: urban (U) or rural (R) |
| `famsize` | Binary | LE3, GT3 | Family size: less than or equal to 3 (LE3) or greater than 3 (GT3) |
| `Pstatus` | Binary | T, A | Parents' cohabitation status: together (T) or apart (A) |
| `Medu` | Ordinal | 0–4 | Mother's education: 0 = none, 1 = primary education, 2 = 5th–9th grade, 3 = secondary education, 4 = higher education |
| `Fedu` | Ordinal | 0–4 | Father's education: 0 = none, 1 = primary education, 2 = 5th–9th grade, 3 = secondary education, 4 = higher education |
| `Mjob` | Categorical | teacher, health, services, at_home, other | Mother's occupation |
| `Fjob` | Categorical | teacher, health, services, at_home, other | Father's occupation |
| `reason` | Categorical | home, reputation, course, other | Reason for choosing the school |
| `guardian` | Categorical | mother, father, other | Student's guardian |
| `traveltime` | Ordinal | 1–4 | Home-to-school travel time: 1 = <15 min, 2 = 15–30 min, 3 = 30–60 min, 4 = >60 min |
| `studytime` | Ordinal | 1–4 | Weekly study time: 1 = <2 hours, 2 = 2–5 hours, 3 = 5–10 hours, 4 = >10 hours |
| `failures` | Integer | 0–4 | Number of past class failures |
| `schoolsup` | Binary | yes, no | Extra educational support |
| `famsup` | Binary | yes, no | Family educational support |
| `paid` | Binary | yes, no | Extra paid classes within the course subject |
| `activities` | Binary | yes, no | Participation in extracurricular activities |
| `nursery` | Binary | yes, no | Whether the student attended nursery school |
| `higher` | Binary | yes, no | Whether the student wants to pursue higher education |
| `internet` | Binary | yes, no | Internet access at home |
| `romantic` | Binary | yes, no | Whether the student is in a romantic relationship |
| `famrel` | Ordinal | 1–5 | Quality of family relationships: 1 = very bad to 5 = excellent |
| `freetime` | Ordinal | 1–5 | Free time after school: 1 = very low to 5 = very high |
| `goout` | Ordinal | 1–5 | Frequency of going out with friends: 1 = very low to 5 = very high |
| `Dalc` | Ordinal | 1–5 | Workday alcohol consumption: 1 = very low to 5 = very high |
| `Walc` | Ordinal | 1–5 | Weekend alcohol consumption: 1 = very low to 5 = very high |
| `health` | Ordinal | 1–5 | Current health status: 1 = very bad to 5 = very good |
| `absences` | Integer | 0–93 | Number of school absences |
| `G1` | Integer | 0–20 | First-period grade |
| `G2` | Integer | 0–20 | Second-period grade |
| `G3` | Integer | 0–20 | Final grade; primary outcome variable in this project |

---

## 6. Methodology

### Data Preparation

The analysis was conducted using the Mathematics dataset (`student-mat.csv`). The dataset was loaded and examined for its structure, variable types, distributions, and data quality.

The analysis focused on predicting **G3**, the final mathematics grade.

### Exploratory Data Analysis

Exploratory data analysis (EDA) was conducted to better understand student performance and relationships among variables.

The analysis included:

- Examining the distribution of `G3`
- Exploring the relationship between study time and final grades
- Comparing parental education levels with student performance
- Examining correlations among numerical variables
- Exploring the relationships among `G1`, `G2`, and `G3`

The exploratory analysis showed that earlier academic performance, particularly `G1` and `G2`, was strongly associated with the final grade.

### Feature Engineering

Two additional features were created to represent aspects of students' academic development and engagement:

- **Academic Progress:** a feature combining standardized G1 and G2 scores to represent both previous achievement and changes in academic performance.
- **Study Engagement:** a composite feature based on study time, attendance, family relationships, and free time.

These engineered features were used together with selected original variables in the predictive model.

### Predictive Modeling

A **Linear Regression** model was used to predict students' final mathematics grade (`G3`).

The predictors included:

- `G1`
- `G2`
- `academic_progress`
- `study_engagement`
- `Medu`
- `absences`

The dataset was divided into training and testing sets using an **80/20 split** with `random_state = 42`.

### Model Evaluation

Model performance was evaluated using:

- **R-squared (R²):** approximately 0.792
- **Mean Absolute Error (MAE):** approximately 1.307
- **Root Mean Squared Error (RMSE):** approximately 2.064
- **Mean Absolute Percentage Error (MAPE):** approximately 10.20% when observations with `G3 = 0` were excluded from the MAPE calculation

The model explained approximately 79% of the variation in final mathematics grades in the test data.

Among the predictors, `G2` showed the strongest positive relationship with `G3`, which is consistent with the fact that G2 represents academic performance immediately before the final grade.

---

## 7. Sharing and Access Information

### Data Availability

The original Student Performance dataset is publicly available from the **UCI Machine Learning Repository**.

- **Dataset:** Student Performance
- **Creator:** Paulo Cortez
- **Dataset DOI:** [10.24432/C5TG7T](https://doi.org/10.24432/C5TG7T)
- **License:** Creative Commons Attribution 4.0 International (CC BY 4.0)
- **Original Source:** [UCI Student Performance Dataset](https://archive.ics.uci.edu/dataset/320/student+performance)

The CC BY 4.0 license allows the dataset to be shared and adapted, provided that appropriate credit is given to the original source.

### Project Repository

This GitHub repository contains:

- The Mathematics dataset used in the project (`student-mat.csv`)
- Project documentation and metadata (`README.md`)

The repository is public so that the project documentation and data can be accessed and reviewed.

### Software and Tools

The analysis was conducted using Python in Jupyter Notebook. Major tools and libraries included:

- Python
- Jupyter Notebook
- pandas
- NumPy
- scikit-learn
- Matplotlib

GitHub and Markdown were used to organize and share the project documentation.

---

## 8. Reproducibility and Limitations

### Reproducibility

The main analytical workflow was:

1. Load `student-mat.csv`.
2. Inspect the dataset structure and variable types.
3. Conduct exploratory data analysis.
4. Create the `academic_progress` and `study_engagement` features.
5. Select `G1`, `G2`, `academic_progress`, `study_engagement`, `Medu`, and `absences` as predictors.
6. Define `G3` as the outcome variable.
7. Split the data into training and testing sets using an 80/20 split with `random_state = 42`.
8. Fit a Linear Regression model using the training data.
9. Generate predictions for the test data.
10. Evaluate model performance using R², MAE, RMSE, and MAPE.

The data source, variable definitions, model type, predictors, train/test split, and evaluation metrics are documented to make the analytical process easier to understand and reproduce.

### Limitations

This project has several limitations.

First, the dataset represents students from only two Portuguese secondary schools. Therefore, the findings should not automatically be generalized to students from other schools, countries, or educational systems.

Second, `G1` and `G2` are grades from earlier periods of the same course and are strongly related to `G3`. Including them substantially improves prediction, but a model that predicts performance before these grades become available could be more useful for a very early warning system.

Third, the `study_engagement` feature is a researcher-created composite measure. Its interpretation depends on the variables and weights used to construct it and should not be treated as a direct measurement of student engagement.

Finally, the relationships identified in this observational dataset represent associations and should not automatically be interpreted as causal effects.

---

## 9. Reflection

### Which Metadata Standard Did I Choose and Why?

I chose **DDI-Codebook** as the metadata standard for this project. I selected it because it is designed for documenting individual research datasets and provides a structured way to describe study information, data files, variables, methodology, provenance, and access information.

This structure is particularly useful for the Student Performance dataset because the dataset contains many coded educational, demographic, family, and behavioral variables. Using DDI-Codebook principles helped me think about the information another researcher would need in order to understand and reuse the data.

### Which Template or Software Did I Use?

I used **GitHub Markdown** to create the README and referred to the **Make a README** guidelines when organizing the document.

GitHub was used to store and share the dataset and its documentation, while Markdown provided a simple way to organize headings, links, lists, and the data dictionary in a readable format.

### What Was the Most Challenging Part of Creating the README?

The most challenging part was creating a clear and accurate data dictionary. The dataset contains 33 variables, and many variables use abbreviated names and coded values. For example, variables such as `Medu`, `Fedu`, `traveltime`, and `studytime` are difficult to interpret correctly without additional documentation.

Another challenge was deciding how much methodological information should be included so that another researcher could understand the analysis without making the README unnecessarily complicated.

### How Did I Overcome These Obstacles?

I referred back to the original documentation from the UCI Machine Learning Repository to verify the meaning and coding of the original variables. I then organized the information into a structured data dictionary containing the variable name, type, possible values or range, and description.

For the methodology section, I documented the major steps of the analysis, including feature engineering, predictor selection, the train/test split, model type, and evaluation metrics. This helped make the project more transparent and reproducible.

---

## References

Cortez, P. (2008). *Student Performance* [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5TG7T

Cortez, P., & Silva, A. M. G. (2008). *Using data mining to predict secondary school student performance*. Proceedings of the 5th Annual Future Business Technology Conference.

Data Documentation Initiative Alliance. *DDI-Codebook*. https://ddialliance.org/ddi-codebook
