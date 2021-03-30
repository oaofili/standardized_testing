# Standardized Test Analysis by Okey Ofili

![alt text](https://ofilispeaks.com/wp-content/uploads/Screen-Shot-2021-02-05-at-11.12.43-AM.png)

### Overview

The SAT and ACT are standardized tests that many colleges and universities in the United States require for their admissions process. This score is used along with other materials such as grade point average (GPA) and essay responses to determine whether or not a potential student will be accepted to the university.

The SAT has two sections of the test: Evidence-Based Reading and Writing and Math ([*source*](https://www.princetonreview.com/college/sat-sections)). The ACT has 4 sections: English, Mathematics, Reading, and Science, with an additional optional writing section ([*source*](https://www.act.org/content/act/en/products-and-services/the-act/scores/understanding-your-scores.html)). They have different score ranges, which you can read more about on their websites or additional outside sources (a quick Google search will help you understand the scores for each test):
* [SAT](https://collegereadiness.collegeboard.org/sat)
* [ACT](https://www.act.org/content/act/en.html)

Several articles and research conducted including this 2017 article by brookings.edu [Race gaps in SAT scores highlight inequality and hinder upward mobility] estimate that in the entire country [in 2017] at most 2,200 black and 4,900 Latino test-takers scored above a 700 in their SAT as compared to roughly 48,000 whites and 52,800 Asians that scored that high. 
Source: https://brook.gs/3jj8C32

Data like this, that point to such significant racial disparity, make the SAT and other standardized exams a largely controversial and sensitive topic for students, administrators and legislators to discuss.

And lately, more and more schools are opting to drop the SAT/ACT requirements for their Fall 2021 applications or choosing to consider external factors (such as hardship) versus just looking at SAT scores.

While these are commendable ... it does not help to fully address the issue, and that is, what changes can be made at the school and legislative level to ensure that at least a majority (currently 43%) of California schools are able to get more than 50% of their students to pass the SAT and other standardized exams.

![alt text](https://ofilispeaks.com/wp-content/uploads/Screen-Shot-2021-02-05-at-11.12.10-AM.png)

### Problem Statement

The state of California has many schools (about 57%) with less than a majority of their students passing the SAT standardized tests. This project aims to first identify the characteristics of poor-performing schools and recommend programs to the state government to help equalize study experiences across the state. And secondly, but more importantly identify the outliers, which are the schools with all the characteristics of a poor performing school that still perform well on the SAT and other standardized tests. This information will be provided to enable the state of California to study these outlier schools and recommend their best practices to other schools in the state.

---

### Datasets

There are 4 datasets included in the [`data`](./data/) folder for this project. 

* (./data/act_2019_ca.csv): 2019 ACT Scores in California by School ([source](https://www.cde.ca.gov/ds/sp/ai/) | [data dictionary](https://www.cde.ca.gov/ds/sp/ai/reclayoutact19.asp))

* (./data/sat_2019_ca.csv): 2019 SAT Scores in California by School ([source](https://www.cde.ca.gov/ds/sp/ai/) | [data dictionary](https://www.cde.ca.gov/ds/sp/ai/reclayoutsat19.asp))

* (./data/ca_poverty_numbers.csv): California Schools Unduplicated Student Poverty – FRPM Data 2014–18 ([source](https://www.cde.ca.gov/ds/sd/sd/filescbedsoraa.asp) 

* (./data/Race_per_school.csv): California School Enrollment by Race, Gender, and Grade. ([source](https://www.cde.ca.gov/ds/sd/sd/filesenr.asp) 

---

### Data Dictionary

|Feature|Type|Dataset|Description|Source
|---|---|---|---|---|
|schools|object|ACT/SAT|California Schools|https://www.cde.ca.gov/ds/sp/ai/|
|districts|object|ACT/SAT|The district's that schools are located in|https://www.cde.ca.gov/ds/sp/ai/|
|countys|object|ACT/SAT|The county's that the schools are located in|https://www.cde.ca.gov/ds/sp/ai/|
|sat_pct_pass_gr12|float64|ACT/SAT|Percentage of Students that met SAT benchmark in both subjects|https://www.cde.ca.gov/ds/sp/ai/|
|act_pct_pass_gr12|float64|ACT/SAT|Percentage of Students that attained an average score greater than or equal to 21|https://www.cde.ca.gov/ds/sp/ai/|
|pct_poverty|float64|Poverty Rates Per School|the first contains the unduplicated count of students who meet household income or categorical eligibility criteria for free or reduced meals (FRPM) per school|https://www.cde.ca.gov/ds/sd/sd/filescbedsoraa.asp|
|pct_asian|float64|Race Per School|Percentage of Asian students|https://www.cde.ca.gov/ds/sd/sd/filesenr.asp|
|pct_black|float64|Race Per School|Percentage of Black students|https://www.cde.ca.gov/ds/sd/sd/filesenr.asp|
|pct_hispanic|float64|Race Per School|Percentage of Hispanic students|https://www.cde.ca.gov/ds/sd/sd/filesenr.asp|
|pct_white|float64|Race Per School|Percentage of White students|https://www.cde.ca.gov/ds/sd/sd/filesenr.asp|
|pct_mixed|float64|Race Per School|Percentage of Mixed-Race students|https://www.cde.ca.gov/ds/sd/sd/filesenr.asp|
|pct_other_race|float64|Race Per School|Percentage of Other Race students, including Filipinos and Native American|https://www.cde.ca.gov/ds/sd/sd/filesenr.asp|
|act_tst_tkrs_gr12|float64|ACT/SAT|Total number of students that took the 2018/19 ACT exam|https://www.cde.ca.gov/ds/sp/ai/|
|enroll_gr12|float64|ACT/SAT|Total number of students enrolled in Grade 12|https://www.cde.ca.gov/ds/sp/ai/|
|sat_tst_tkrs_gr12|float64|ACT/SAT|Total number of students that took the 2018/19 SAT exam|https://www.cde.ca.gov/ds/sp/ai/|
|school_score_class|category|N/A|Categorical performance of each school|N/A|
|school_pov_class|category|N/A|Categorical number of students on Food assistance programs|N/A|

---

### Observations

![alt text](https://ofilispeaks.com/wp-content/uploads/heatmap.png)

*Interpretation: The above image shows that the percent pass rate of SAT per school is strongly related to the percentage of students on Food assistant programs.*

![alt text](https://ofilispeaks.com/wp-content/uploads/Screen-Shot-2021-02-05-at-11.13.33-AM.png)

*Interpretation: The above image shows the strong negative correlation of School Poverty Rates to School SAT Percent pass rates. Utilizing the Percentage of Hispanic Students in schools as the Hue, we see that they are clustered in the bottom right corner of the Graph. This indicates that most schools with Hispanic students have a high poverty rate*

---

### Conclusions

Based on my research, these are my key takeaways and recommendations

1. **Poverty not Race:** Although California Schools with significantly high population of white students (67% correlation) tended to do better on the SAT, while schools with a significantly high population of Hispanic students (-81% correlation) tended to fair less on the SAT. Race was not as strong as a determining factor for performance as poverty/income (86% correlation). 

2. **The Outliers: Finding Principal Esau Berumen** For schools with more than 70% percent of their students on food assistance program, the top 5 schools had at least 6 out of 10 of their students passing the SAT exam! Personal research into these schools showed that they had principals that had been in the school system for over 5 years. Principal Esau Berumen the current principal of Hawthorne Math & Science Academy had been teaching at the school since 2003 as a biology teacher. While Yolanda Gardea the principal of Van Nuys Senior High has been at the school since 2012. This might not actually be a pattern, but it begs the question of what could be if we surveyed each of these schools. Unfortunately, this is beyond the scope of this project.

![alt text](https://ofilispeaks.com/wp-content/uploads/Screen-Shot-2021-02-05-at-11.11.47-AM.png)

3. **Migrations to Suburbs** It was also noticed that majority of the poor performing schools were located near city centers, especially in Los Angeles ... while high performing schools (with at least 75% of their students passing the SATs) were located in the suburbs. This is a trend that has been observed in major cities like Houston.

![alt text](https://ofilispeaks.com/wp-content/uploads/Screen-Shot-2021-02-05-at-11.13.18-AM.png)

---

### Recommendations
Based on my research, these are my key takeaways and recommendations

1. **The Foodstamps Limit** We recommend that the California Government finds ways to slow the movement of families to the suburbs, such as increasing property taxes further from city centers (especially the city of Los Angeles) or giving incentives for families to stay within the cities. But more importantly, a law should also be passed that caps the limit of students on food assistants programs at each school to 50%. The excess students should be bussed to other schools, this would help even out the number of students within the poverty group per school.

2. **Beyond The Computer** More significantly we recommend that the State of California sends Education ministry officials to the outliers schools to study what the schools are doing right. As well as bringing Principals, staff and students from these successful schools together for a 1 week workshop to develop a potential standardized playbook to help schools in similar circumstances replicate their strategies for success.
