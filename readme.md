# PISA 2012 DATASET EXPLORATION

## by ABDELHAMID TEBBA

## Project overview:

In this exploration, I wanted to know the variables that might help explain the scores obtained by students in reading, maths and science. In this regard, I used both quantitative and qualitative variables that I have grouped into two categories: personal facors and environmental factors. But my main focus was on three categorical variables: gender, country groups and parents working status.

## Dataset:

PISA, the OECD Programme for International Student Assessment, is a survey that takes place every 3 years with the aim to see how well are the skills and knowledge of 15-16 year orld students in reading, mathematics and science.

The initial dataset of the 2012 edition contains more than 600 variables and 485490 observations. I reduced this data set to 21 variables, selected after reading the 2012 PISA Report. This rearranged and cleaned dataset include, inter alia, the following features: the scores obtained, the contry group (OECD or Non-OECD), the gender, the current occupation status of both parents, the economic and social index and the average time spent at school on the three assessed subjects.

**The selected variables were saved in a csv file (pisa_sub.csv) to facilitate the reloading of the data when necessary.

The complete list of these variables is summerized as follows (Note that this is a renamed list):

* Country_code: 3 digit country code
* oecd: whether a country is part of the oecd or not (oecd stands for the Organization for Economic Cooperation and Development)
* student_id
* grade: international grade
* gender: Male or Female
* mother_job: current job status. These status are classified as "looking for a job', 'Other', 'full-time', 'part-time'
* father_job: same as mother job
* min_lang_class, min_math_class and min_sci_class are the average time (minutes) spent in class per each subject
* teacher_support: an index of teaching quality based on 5 items
* age: age of the students (b/W 15.1 and 16.3)
* eco_social_index: index of economic, social and cultural status. This index was computed through three subcomponents, namely home possessions, heighest parental occupation and highest parental education
* parent_status: heighest parental occupation
* outside_studytime: amount of time spent studying outside of school
* parent_education: highest parental education expressed in years
* teacher_relation: the student/teacher relation based on 5 item parameters like extra help, interest, treatments...
* lang_home: The first language learned at home. This can be either 1) Test language or other official dialect, 2) Test language or other official dialect and another language, 3) Language other than the test or other official language
* PV1MATH, PV1READ, PV1SCIE: These are plausible values used to compute the final score of students. There are 5 plausible values for each of the subjects assessed, and PISA recommends to analyze each one independently and then aggregate the results to obtain the final estimate. However, the 2009 PISA Data analysis manual clearly states that "using one plausible value or five plausible values does not really make a substantial difference on large samples. During the exploratory phase of the data, statistical analyses can be based on a single plausible value". This is why I chose one plausible value for each subject.

## Cleaning process:

* I renamed the columns names so as to make it easy for me to analyze the data and for any reader to understand the meaning of the labels
* I changed the values of two variables (ST15Q01, ST19Q01), which correspond respectively to mother's and father's current occupation 
* I changed the data types of the following variables: oecd, gender, mother_job, father_job, lang_home
* I created three addtional columns: 1) one for the average score which is the mean of the three plausible values I got in my dataset, 2) the second for age category. I grouped in this column all the ages into 15 and 16 years old. 3) I segmented the economic and social index var into 4 categories (very low status, low status, medium status, high status). Medium status is ranged from 1 point below and above the mean (-1 < -0.19(mean) < 1). The high status is set to be the (1,4] interval. Equally on the opposite side, the low status is in the (-4,-1] interval, and the very low status corresponds to any student below the low status range down to the min value of the index
 
 **After the cleaning process I saved the cleaned dataset in a new csv file (pisa_sub_new.csv)**.

## Summary of Findings:

In this project, I found that there was no strong correlation between the numeric variables and the scores obtained by student. Some categorical variables seem to have, to a certain level, a relationship with the students performance, like for example whether the country is part of the OECD or not. I also noticed a slight difference in the scores based on the gender. In this regard, Female students in oecd countries and non oecd countries perform well in reading as compared to boys, while in maths it is the opposite. An other feature which explains visibly the scores obtained is the parents occupation status. In fact, students with full time working parents score better in comparison to students with other different parent status. On the other hand, the less performers, on average, are the ones with no working parents.   


## Key Insights for Presentation:
OECD countries have higher average scores than Non-OECD countries. This shows how belonging to the OECD club, whose members are developed countries, has an effect on the PISA scores. It may be consistent with the fact that OECD countries have a better education system.
Also, the parents occupation status and the economic and social level seem to have a visible effet on the scores obtained. Evidently, a parent full-time status and a high social and economic level are synonym of a somewhat security, which is likely to affect the performance of children.

## Sources:

* PISA 2012 Technical Report
* 2009 PISA Data analysis manual
