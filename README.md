# Evaluating-leading-contributors-of-infant-mortality
Coursework for Data Analysis and Machine Learning Course

**Introduction:**
The death of children under the age of one is known as infant mortality. The infant mortality rate
is the number of infant deaths for every 1,000 live births. The infant mortality rate is an essential
indicator of a society's general health, in addition to providing crucial information regarding
maternal and baby health. Infants die for a variety of reasons, including various infections,
maternal difficulties, injuries, genetic disorders, and so on. However, if we can identify the factors
that can be avoided, we may try to lower the infant mortality rate to a minimum.

**Methodology:**
For the project, I have used, CRISP DM framework.

**Objective:** The goal of this research is to create a Machine Learning model that predicts the
preventable major contributors of infant mortality based on historical childbirth and death data.

The majority of research is focused on the causes of infant death including government agencies
The Centers for Disease Control and Prevention (CDC). However, the secondary and tertiary causes of infant mortality are included in our
research. In our study, we have particularly looked at the International Classification of Diseases (ICD) to find out the preventable contributors.
“Causes” and “Contributors” might sound similar, but there is a significant differenc between
them.

• A cause immediately leads to death.
• A contributor, on the other hand, is a risk factor that increases the likelihood of mortality.

For Example,mother’s with high cigarette consumption might be a contributor towards the infant
mortality, however the direct cause might be respiratory malfunction in the child.

**Data Understanding:**
Data Source: We have collected out data from CDC’s National Center for Health Statistics. This is
a portal for the online data dissemination activities of the Division of Vital Statistics, including
both interactive online data access tools and downloadable public-use data files. We have used
the “Birth Cohort Linked Birth – Infant Death Data Files 2013” for our study since the STRATA
data format was only available for 2013.
Since this dataset had complex medical jargon for non-medical people like ourselves, we had to
get a proper understanding of these terms to understand the dataset. We have used ample time
for data understanding which is a crucial part of the project.
**Data Preparation:**
**Data Preprocessing:**
• Since data was in STRATA format, we used “pyreadstat” API and read the DTA file
• Then we merged both the birth & death datasets.
• Since the data for death class was 0.5% of that of birth class, we did oversampling.
• For NaN data value imputation, we replaced the NaN value with zero.
• Since the dataset has categorical values, we used One-Hot-Encoding. We didn’t use any
scaler as we did the OHE.
**Feature engineering:** As feature engineering part, we removed the columns based on the
following criteria including duplicate values, reporting flag, values less than 10%, features not
relevant to our objective. We also set out the target variable “Death” to aid in data modelling &
evaluation.
**Modeling:**
Model Selection: For this project, I have used “Random Forest Classifier” as my model since it
is known to be best with the categorical values and requires minimal data pre-processing, also
since it is an ensemble model, it has higher accuracy values.
**Hyperparameters Optimization:** Different hyperparameters were employed to
enhance optimization. n estimators, max depth, min samples split, and max features are some
examples. We utilized Randomized Search for the hyperparameter optimization method. This
method searches the grid space randomly instead of doing an exhaustive search i.e. it tries
randomly selected combinations of parameters. Some hyperparameters are often more
important than others. Random search enables for considerably more precise discovery of good
values for critical variables. The accuracy is 89 percent.
Evaluation:

For True ”Live” record and True “Death” records, the value is high from the False results.
**Deployment:** Purpose of applying this machine learning algorithm was to find the major
contributers to the infant fatality in United State. Through my work, following feature stood out
that contributed the most:
• Newborn affected by maternal hypertensive disorders: This feature refers to newborn affected by maternal hypertensive disorders. It includes mothers’ 1) chronic hypertension, 2) preeclampsia-eclampsia, 3) preeclampsia superimposed on chronic hypertension, and 4) gestational hypertension
• Birth asphyxia: This refers to birth asphyxia which means lack of oxygen and blood flow to the brain. It can happen for many reasons, some reason might be A serious infection in the mother or baby, high or low blood pressure in the mother, Problems with the placenta separating from the womb too soon etc.
• Neonatal aspiration syndromes: This is Neonatal aspiration syndromes which means persistent pulmonary hypertension
• Newborn affected by incompetent cervix: When mother has cervical insufficiency, newborn affected by incompetent cervix which lead to death
• Newborn affected by other maternal conditions which may be unrelated to present pregnancy
• Gonococcal Infection: This refers to Gonococcal infection which is a sexually transmitted disease caused by an infection due to unprotected sexual contact
• Complications of Labor and Delivery (Breech Position): This indicates any complications of Labor and Delivery (Breech Position)

**Challenges:**
I selected the "Birth" and "Death" datasets from 2013, because only the 2013 dataset was accessible in DTA format, and we retrieved the data using the Pyreadstat API.
Another issue was that the data was comprised of two reporting files, one of which utilized the 2003 revision of the United States Standard Certificate of Live Birth (revised) and the other of which used the 1989 Standard Certificate of Live Birth (unrevised). As a result, duplicate rows such as RECODE values and extra reporting flags made both the "Birth" and "Death" datasets extremely complex.
When it comes to the model we utilized, it has some drawbacks, despite the fact that it provided us with a decent accuracy score. One of the disadvantages is that it is a black-box model, meaning that users cannot interpret its internal workings. It is also difficult to comprehend. Compiling a huge number of trees can take much longer than anticipated.The result's interpretation is a little vague. The interpretation should be clear because our topic deals with a very sensitive issue.
**Future work:**
I only worked with the 2013 data file because the most recent and historic data were not available in a straightforward data format. We can train our model more effectively if we can use datasets from other years.
