# Students Adaptability Level in Online Education
This is the final project from the data science bootcamp I attended. In this final project, I analyzed information on how students adapted to online learning as a result of the COVID-19 pandemic in Bangladesh. I got the dataset from Kaggle and analyzed it independently. Mentors and fellow participants reviewed the results of the project.

## ABOUT DATA
- **Data Title** <br>
  Students Adaptability Level in Online Education
- **Kaggle Link** <br>
  https://www.kaggle.com/datasets/mdmahmudulhasansuzan/students-adaptability-level-in-online-education/data
- **About Data** <br>
  Online Education has become a buzzword since the COVID-19 hit the World. Most of the educational institutions went online to continue educational activities while developing countries like Bangladesh took a significant period of time to ensure online education at every education level. <br>

  Students of several levels also faced many difficulties when they got introduced to online education. It is important for the decision makers of educational institutions to be informed about the effectiveness of online education so that they can take further steps to make it more beneficial for the students. <br>
- **Columns** <br>
  - Gender: Gender type
  - Age: Age range of student
  - Education Level: Education institution level
  - Institution Type:  Education institution type
  - IT Student: Studying as IT student or not
  - Location: Is the domicile of the students in Bangladesh.
  - Load-shedding: Level of load-shedding (power outage)
  - Financial Condition: Financial condition of family
  - Internet Type: Internet type used mostly in device
  - Network Type: Network connectivity type
  - Class Duration: Daily class duration
  - Self Lms: Institution’s own LMS availability
  - Device: Device mostly used in class
  - Adaptivity Level: Adaptability level of the student

  **Target:** Adaptivity Level

## EXPECTED OUTPUT
**Objective:**
Understand and analyze the factors that affect students' adaptation to the efficacy of online learning methods.
- Is gender, network type, and education level highly significant?
- What are the biggest barriers to adapting to online learning?
- Which factors are interconnected and impact student adaptation?

## ⚙ PROCESS ⚙
1. Import Libraries
2. Data Preparation
3. Data Processing
   - Null check
   - Duplicate check
4. Data Manipulation
   - Change data type: Object to Numeric (1 0)
   - Change data type: Object to Categorical
   - Change data type: Categorical to Ordinal Numeric
5. EDA
   - Data Understanding
   - Hipotesis : Uji Chi Square
   - Uji Kendall's Tau

## **📊 Dataset Description 📊**
🔴 Based on the data used, the dataset consists of ```14 columns```, ```1205 rows```, Data type ```object```, there is ```no null/Nan``` on the data, I found ```949 duplicate``` data and the target value of this data is Adaptivity Level. For the duplicate data found, I took no action because the dataset is categorical, so it's highly likely to have duplicate data. <br>

🔴 Because all dataset types are objects, I started by converting to categorical type. Then change some to boolean and ordinal numeric datatype. However, for EDA, I kept and used the original categorical dataset.
- Boolean numeric:
  - ```IT Student```
  - ```Self Lms```
- Ordinal numeric:
  - ```Load Sheding```: Low = 1; High = 2
  - ```Financial Condition```: Poor = 1; Mid = 2; Rich = 3
  - ```Network Type```: 2G = 1; 3G = 2; 4G = 3
  - ```Adaptivity```: Low = 1; Moderate = 2; High = 3
  - ```Age```: 26-30 = 6; 21-25 = 5; 16-20 = 4; 11-15 = 3; 6-10 = 2; 1-5 = 1
  - ```Class Duration```: 3-6 = 2; 1-3 = 1; 0 = 0

## **📊 Understand the Data 📊**
**Adaptivity Level**
- Only 8.3% of students can adapt well to online learning methods.
- Almost 40% face difficulties in adapting to online learning methods.
- The most common adaptation level is at the Moderate level
  
**Gender**
- More than half of the data population are males.
- When observed by 'Gender', males show better adaptation ability compared to females.
- The high adaptivity level for males is 10.7%, while for females it is only 5.4%.

**Age, Education and IT Student**
- Students under the age of 15 account for a total of 40.2%.
- Students aged between 16-20 years old make up 23.1%
- At first, I thought there were no students from 'School' (Elementary, Junior, and Senior High) learning IT directly, but it turns out there are, although not as many as in universities.
- For now, we can ignore this education level because almost the majority of the data population are school children (43%) who are not learning IT.

**Location**
- The dominant population is in Bangladesh with a high adaptivity rate of 9.8%.
- The population outside Bangladesh with high adaptivity is 3%.

**Financial Condition**
- The dominant population for this financial condition is the middle class, with the most common adaptivity level being moderate, followed by low adaptivity, and the smallest being high adaptivity.

**Network Level**
- The 'High' Adaptivity level for Network 4G is much higher compared to 3G and 2G.
- The dominant Adaptivity level for Network 4G is 'Moderate'.
- Location factor also appears to be associated with the network.
- It is evident from the graph that students living in Bangalore have better 4G and 3G internet networks compared to those outside Bangalore.

**❓DEEP DIVE QUESTION❔**
1. How does gender affect adaptability level?
2. Is Network Type the most important element influencing Adaptivity Level, among others variabel?
3. Does a better network type imply a higher level of adaptivity?
4. What is the relationship between IT student and adaptability level?
  
## ✅❌ HIPOTESIS
**Chi-Square Test**<br>
Based on the observed data, I'd like to find out the association between Adaptivity Level and the following features:
1. Gender
2. IT Student
3. Network Level.
  
    - H0: There is no significant association between the two categories.
    - H1: There is a significant association.

I used the chi-square test with a p-value of 0.05.

**Result** <br>
I rejected the null hypothesis (H0) since the p-values for all three variables are less than 0.05. The chi-square test findings show that the three factors are significantly related to the ```Adaptivity Level```.
- p-value for ```Network Type``` : 4.367322677925763e-06
- p-value for ```Gender``` : 0.0011997056689743298
- p-value for ```IT Student``` : 5.553333138404098e-05

Follow up questions:<br>
1. How about the other variables? Do they all have associations?
2. Which variable affects the Adaptivity Level the most significantly?

**End Result for chi-square test***
Based on the comprehensive analysis, it has been determined that every variable is connected to the Adaptivity Level. Among the variables, the Financial Condition p-value is the most significant, since it approaches 0 in comparison to the other ones. For Financial Condition, the p-value is 4.391228197442381e-50.

**Kendall's Tau**
