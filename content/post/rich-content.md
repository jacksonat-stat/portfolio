+++
author = "Hugo Authors"
title = "TIMSS Economic and Educational Background Research paper"
date = "2020-12-17"
description = "A brief description of Hugo Shortcodes"
tags = [
    "TIMSS",
    "math achievement",
]
+++
### Educational and economic background variables related to mathematics achievement: A comparative study in Singapore, Ireland, and Jordan
#### By: 2020 SSOR 690 Research Team

<!--more-->
---
### 1. The purpose of the project 
The purpose of this project was to examine the link between grade 4 students’ educational and economic background and their mathematics achievement among Singapore, Ireland, and Jordan by using the Trends in International Mathematics and Science Study (TIMSS) 2015 datasets. An overall model built from the three countries acted as a proof of concept for the broader goal of collecting a substantial random sample, spanning many countries, that can generate a model with universally strong predictive ability. Recognizing the common economic factors that influence variability in a student’s mathematical performance gives education experts important metrics for identifying disadvantaged communities and students that may be at risk of lagging behind in mathematics. The following project question guided our modeling and research: Is the economic and educational background of parents a good predictor of mathematical achievement using TIMSS 2015 data for fourth-grade students from Ireland, Jordan, and Singapore?
### 2. Literature review
It is widely accepted that students from low socioeconomic status (SES) families lag behind their high-SES peers in academic performance (Perry & McConney, 2010; Sirin, 2005). To investigate which specific aspects of students’ family SES significantly influence their mathematics achievement, we reviewed relevant literature regarding the link between student educational and economic backgrounds and their mathematics achievement among Singapore, Ireland, and Jordan. Based on the broader literature and the nature of items in TIMSS questionnaires, we selected variables of interest in this project.
#### *2.1. Review in Singapore.*
Empirical work has examined Singaporean students’ economic, social and cultural status (ESCS) with their academic learning outcomes, including academic resilience (Cheung et al., 2014), mathematical literacy performance (Cheung, 2017), and mathematics achievement (Thien & Ong, 2015). Using the Programme for International Student Assessment (PISA) datasets, Thien and Ong (2015) found that for Singaporean students, one standard deviation increase in ESCS was associated with a 27-point increase in their math scores, based on the results of multilevel modeling. Specifically, the ESCS referred to an index that included the highest parental occupational status, the highest parental educational attainment, and home possessions which was the number of books at homes, home educational, and cultural possession (OECD, 2014). Similarly, another study using TIMSS datasets found that the odds for students in Singapore becoming academically successful was three times higher for those not from disadvantaged homes (Sandoval-Hernández & Białowolski, 2016). The authors operationalized disadvantaged students if ascribed as ‘‘few resources’’ in the home educational resources index which was included in the TIMSS database and was created from student reports about three home resources: (a) number of books in the home, (b) availability of two home study supports and (c) parental education (mean = 10, standard deviation = 1). On average, students in the ‘‘few resources’’ category reported that they had 25 or fewer books in the home, neither of the two home study supports (own room and internet connection), and that neither parent had achieved more than completion of upper-secondary education (Mullis et al. 2012, p. 180). Similarly in another study (Mohammadpour, 2012), students’ home educational resources showed to be a positive predictor (b = 9.77, p < .05) of mathematics achievement among Singaporean students.

#### *2.2. Review in Jordan.*
Hammouri (2004) examined a comprehensive set of attitudinal variables related to student mathematics achievement in Jordan and found among all the attitudinal variables examined, mother’s perception of importance in math learning was the strongest and statistically significant predictor of student mathematics achievement. Another study identified the highest level of parents’ education strongly related to student mathematics achievement in Jordan (Sabah & Hammouri, 2010). However, using the Health Behavior in School-Aged Children (HBSC) data, Saleh and colleagues (2019) examined demographic variables including type of school, mother's and father's education and occupations with student academic performance and school satisfaction in Jordan, and they excluded mother's and father's education and occupations during the linear regression modeling. 
#### *2.3. Review in Ireland.*
Many studies have examined factors that influence Irish students’ mathematics achievement (Gilleece et al., 2010; Higbee & Thomas, 1999; O’Shea & Leavy, 2013). Gilleece and colleagues (2010) found that at student level, home language, intention to leave school early, socioeconomic status, grade level, cultural capital, and books in the home are significantly associated with achievement in mathematics and science. At school level, only school average socioeconomic status is statistically significant in the models predicting student achievement.
On the basis of the existing literature, we selected diverse variables related to student socioeconomic status from TIMSS student, home, and mathematics questionnaires. Detailed measures are presented in the following sections.

### 3. Method
#### *3.1. TIMSS Dataset*  
The International Association for the Evaluation of Educational Achievement (IEA)'s TIMSS dataset was used in this project and measures trends in mathematics and science achievement at the fourth and eighth grades. Conducted on a regular 4-year cycle, TIMSS collects a rich array of background information to provide comparative perspectives on trends in achievement in the context of different educational systems, school organizational approaches, and instructional practices. This international assessment is given to various countries to evaluate students’ academic achievement from diverse aspects. In addition to the mathematics evaluation, TIMSS administers 4 questionnaires: the student questionnaire, the home questionnaire, the teacher questionnaire, and the school questionnaire. The variables we selected were derived from these questionnaires.
#### *3.2. Measures*
We included a comprehensive set of variables related to students’ educational and economic backgrounds and socioeconomic status. Table 1 shows the description of the variables of interest in this project and the questionnaires where they were selected. 
Response variable: student mathematics achievement (continuous). The overall math achievement scores available in the TIMSS 2015 dataset were used to represent students’ mathematics achievement in this project. Notably, considering the practical issue of large-scale data collection, students are tested with only one booklet out of 14 TIMSS booklets that are packaged from the entire assessment pool of mathematics items. Therefore, in order to estimate the most accurate and precise mathematics skills of students, mathematics achievement in the TIMSS dataset is represented in five plausible values (PVs) that are imputed based on item response theory which estimates students’ latent general abilities (Foy & Yin, 2015). Following the approach of using all five PVs in past studies, we took the mean of all five PVs to represent student mathematics achievement in this project.
Predictor variables: a comprehensive set of SES variables (ordinal). As mentioned above, based on the literature review and the nature of the variables, we selected three variables from the student questionnaire (e.g., number of books at home, home language), nine variables from the home questionnaire (e.g., parental highest education and occupation), and two variables from the mathematics questionnaire (e.g., extra tutoring), to fully capture the influentially educational and economic background variables associated with educational inequality. All the variables were based on a Likert scale rating. 
#### Table 1.  *Description of the predictor variables of interest in this project.*

![table 1](/images/table1.PNG)

### *3.3. Data analysis* 
All the analyses were carried out in SAS or R programming. First, descriptive statistics and ANOVA regarding the differences in mathematics achievement among students from the three countries were run. Only data with complete entries for all variables under consideration were used for analysis, resulting in 5115 Singapore data points, 2732 Jordan data points, and 2724 Ireland data points for a total dataset of n = 10571 eligible for analysis. Next, linear regression was conducted to examine the model as follows. Specifically, in our model, student mathematics achievement is Y (response variable), and the selected educational and economic background variables are X’s. 
First, assumptions were checked for error normality, error homogeneity, and predictors’ multicollinearity in each country. The Q-Q plots followed a diagnostic line (see Appendix, Figure 1) and all the  variance inflation factor (VIF) values were smaller than 4. Thus, all assumptions were validated.
Next, we conducted sequential model selection. All 14 variables were tested in SAS programming with a global F test. We used backwards, forwards, and stepwise procedures to choose the final model. In the forward procedure, one begins with a null model involving none of the variables, and sequentially adds the variable with the largest partial F-statistic (and therefore lowest p-value) until no more variables that meet a specified threshold of significance remain. Backward elimination employs a similar idea; however, the starting model is a full model containing all of the possible predictor variables of interest, where the lowest partial F-statistic (or highest p-value) is removed from the model until no variable that lies above the p-value threshold remains. The stepwise procedure combines the techniques of forward selection and backward elimination, meaning that as variables are added to a model, the newly added variable is considered along with all other variables present in the model for removal based on the manner in which backward elimination is done. Lastly, we validated our final model using all data separate for each country. 

### 4.  Results
#### *4.1. Descriptive statistics and ANOVA results*
Figure 1 showed the ANOVA results of students’ mathematics achievement in Singapore, Ireland, and Jordan. From the mean difference comparison, we can see that the three countries represent three levels of student math achievement, with Singaporean students having a median  score of 633.96 , Irish students having a median score of 554.99 and Jordan students having a median score of 385.85. 
![figure 1](/images/figure1.PNG)
Figure 1. Mathematics scores comparison in three countries.

### Table 2. *Descriptive statistics of students in Singapore, Ireland, and Jordan.*
![table 2](/images/table2.PNG)
Figure 2 outlines the distribution of math test scores for the overall dataset, as well as percent responses for each predictor variable from the surveys in the regression model. The math score histogram is left skewed, with a mean of 559.51 and a median of 574.43. The country with the largest representation in the overall dataset was Singapore, and it was one of the highest scoring countries on the math exam for the year’s dataset; in consequence, the need to gather more data from a broader collection of countries should we move beyond a proof of concept stage is highlighted by this fact. With a sufficiently large random sample, it can be expected that the mean math scores would display a more normal behavior and that the predictive success range of an overall model would increase. 

The predictor variables are also given, where survey answers were represented as integers corresponding to the order in which the response options are presented in the TIMSS survey. Again, for the limited dataset the overrepresentation of Singapore should be taken into account with these results, where fields such as the parental education background would likely be strongly influenced, and not necessarily representative of a general country or student population. Certain trends that hold true in most countries such as the difference in employment status between mothers and fathers are indicated, as well as educational backgrounds between parents and type of occupation. Though 37.81% of the mothers in the dataset were either explicitly not employed or responded “not applicable” to their employment status, the occupations of the mothers that were employed were often professional, associate professional, or corporate roles at 34.10% of all occupation options. It is also clear that most parents (81%) within the dataset have the expectation that their child will complete an undergraduate education or higher, suggesting that parents generally place a strong value on their child’s education even when the parents have not necessarily attained that level of education themselves. Of the students that participated in extra lessons or tutoring within the last twelve months, the most common response to how many months have been spent in tutoring was “more than eight months” at 20.85%. From the overall student population, 16.95% were reported to be in tutoring “to excel in class” and 18.00% “to keep up in class.” 

![figure 2](/images/figure2.PNG)
Figure 2. Histogram of model variables

#### 4.2. Regression models
Table 3 showed the predictive effects of the significant variables. From the final model, children’s book (b = 28.30, p < .0001), language spoken at home (b = 27.47, p < .0001), and home education expectation (b = 21.11, p < .0001) were shown to be the most influential predictors of students’ math achievement scores in the presence of all the other variables in the model. Additionally, results showed that 49.72% of the variability in students’ mathematics achievement was explained by our final overall model (F = 803.11, p < .0001, R square = .4972). 

#### Table 3. *Estimates of linear regression coefficients in models for mathematics achievement scores.*
![table 3](/images/table3.PNG)

#### *4.3. Cross validation*

In order to perform cross validation of the overall model, the coefficients of the overall model were used in order to predict the mean math scores of  the Singapore, Jordan and Ireland datasets separately. The correlation coefficient between the predicted mean math scores of the overall model and the actual math scores was calculated in SAS or R. Lastly, the following hypothesis test was used to validate the model:

![hypothesis](/images/hypothesis.PNG)
### Singapore. 
The cross validation SAS output is included  below in table 4. The correlation coefficient between the actual mean math scores and the predicted mean math scores was 42.6% suggesting a weak to moderate relationship. A p-value of <.00005 was produced. This resulted in a  rejection of the null hypothesis and it gave evidence that ρ is greater than 0. The overall model was a good model when used against the Singapore data.

#### Table 4. *SAS output for Singapore PROC CORR model validation*
![table 4](/images/table4.PNG)

A further analysis of the errors found that the overall model on average was able to predict within 10.8% of the actual Singapore mean math score and the distribution of the errors can be seen below (Figure 3). The distribution is right skewed, the median of the errors is 9.47% and the spread [IQR] of the errors is 10.7%. Given how small the spread is within the errors, this gives a higher degree of accuracy with the prediction of the Singapore Math scores.
![singapore histogram](/images/singapore-histogram.PNG)
![singapore boxplot](/images/singapore-boxplot.PNG)
#### Figure 3. Histogram and Boxplot of errors for Singapore data

### Jordan. 
The overall model was used to generate predictions of math test scores in the Jordan dataset. A correlation of .4722 between the observed test score values and the predicted scores from the overall model was computed, and so the null hypothesis that ρ = 0 was rejected at p < .001 and it was concluded that there is sufficient evidence that the overall model’s predictions have a nontrivial relationship with the observed test scores in Jordan. Since a majority of the dataset comes from Singapore, the implications of a model from such a dataset still successfully validating for Jordan—a country that differs greatly from Singapore in educational outcomes— are promising because it demonstrates the feasibility of applying these predictor variables broadly, even in the limited proof of concept dataset we constructed. 

![Jordan histogram and boxplot](/images/jordan.PNG)
#### Figure 4. Histogram of errors of Jordan data

The median of the errors in prediction for Jordan are 14.58%, and the spread (IQR) is 17.6%. The slightly higher median and spread in comparison to Singapore may be owed to Singapore’s strong influence in the dataset, though these results ultimately do show a moderate to strong predictive ability. Further work may be done in identifying individual students, or groups of students, where prediction was not as successful to investigate any unique factors that may not have been accounted for in the overall model. 

###Ireland. 
To generate the prediction of math scores within Ireland  the overall model was used. The correlation between the generated predicted scores and the observed results from the Ireland data set generated a correlation of 0.410. 

#### Table 5. *SAS output for Ireland PROC CORR model validation*
![table 5](/images/table5.PNG)
With a p-value < 0.001 The null hypothesis that ρ = 0 was rejected and it was concluded that there is sufficient evidence that the overall model’s predictions have a relationship with the observed test scores from Ireland. Therefore,  it shows proof of concept that an overall model containing three countries that differ in test scores can be used as a predictor. Furthermore, highlighting the importance of the chosen variables in predicting test scores.
![ireland histogram and boxplot](/images/ireland.PNG)
#### Figure 5. Histogram of errors of Ireland data

Analyzing the data for Ireland showed that the average prediction was within 10.49% of the observed data. The median of the errors being 8.3% with an IQR of 10.49%. These figures show that the Ireland data can be predicted with a high degree of accuracy from the overall model.  
### 5. Conclusion
The results detailed in the prior section confirmed that there was a link between grade 4 students’ educational and economic background and their mathematics achievement. More importantly, the results also confirmed that the student’s test scores could be accurately predicted from the socioeconomic data of the TIMSS questionnaire. The variables that were used in the final model are listed in Table 3 of the paper. All the variables studied, with the exception of Home Environment, were  important factors to consider in predicting students' mathematics achievement. Language, Tutoring attendance, Length of tutoring, Father’s education, Mother’s education, Mother’s occupation, Father’s occupation, Educational expectation and whether books/children’s books exist in the home from the Student and Home questionnaire, respectively, were found to have positive effects on mathematical achievement. Father’s employment situation, Mother’s employment situation and whether books exist in the home from the Home questionnaire were found to have a negative effect on mathematical achievement. Given that only three countries were studied,  this project is not exhaustive of the total effects of parental educational/economic background on student mathematics achievement but it does provide a proof of concept for creating a world-wide study. 


### Reference
Cheung, K. C. (2017). The effects of resilience in learning variables on mathematical literacy performance: A study of learning characteristics of the academic resilient and advantaged low achievers in Shanghai, Singapore, Hong Kong, Taiwan and Korea. Educational Psychology, 37(8), 965-982.

Cheung, K. C., Sit, P. S., Soh, K. C., Ieong, M. K., & Mak, S. K. (2014). Predicting academic resilience with reading engagement and demographic variables: Comparing Shanghai, Hong Kong, Korea, and Singapore from the PISA perspective. The Asia-Pacific Education Researcher, 23(4), 895-909.

Foy, P., Arora, A., & Stanco, G. M. (2017). TIMSS 2015 user guide for the international database. Chestnut Hill, MA: TIMSS & PIRLS International Study Center, Boston College.

Foy, P., & Yin, L. (2015). Scaling the TIMSS 2015 achievement data. In M. O. Martin, I. V. S. Mullis, &amp; M. Hooper (Eds.), Methods and procedures in TIMSS 2015 (pp. 13.1-13.62). Chestnut Hill, MA: TIMSS &amp; PIRLS International Study Center, Boston College.

Gilleece, L., Cosgrove, J., & Sofroniou, N. (2010). Equity in mathematics and science outcomes: Characteristics associated with high and low achievement on PISA 2006 in Ireland. International Journal of Science and Mathematics Education, 8(3), 475-496.

Higbee, J. L., & Thomas, P. V. (1999). Affective and cognitive factors related to mathematics achievement. Journal of Developmental Education, 23(1), 8.

Mullis, I. V., Martin, M. O., Foy, P. & Arora, A. (2012). TIMSS 2011 International results in mathematics. Chestnut Hill, MA: TIMSS & PIRLS International Study Center Lynch School of Education, Boston College.
OECD (2014). PISA 2012 results: What students know and can do—student performance in mathematics, reading and science, vol I, Rev edn. OECD Publishing, Paris.

O’Shea, J., & Leavy, A. M. (2013). Teaching mathematical problem-solving from an emergent constructivist perspective: The experiences of Irish primary teachers. Journal of Mathematics Teacher Education, 16(4), 293-318.

Perry, L. B., & McConney, A. (2010). Does the SES of the school matter? An examination of socioeconomic status and student achievement using PISA 2003. Teachers College Record, 112(4), 1137-1162.

Sabah, S., & Hammouri, H. (2010). Does subject matter matter? Estimating the impact of instructional practices and resources on student achievement in science and mathematics: Findings from TIMSS 2007. Evaluation & Research in Education, 23(4), 287-299.

Saleh, M. Y., Shaheen, A. M., Nassar, O. S., & Arabiat, D. (2019). Predictors of school satisfaction among adolescents in Jordan: A cross-sectional study exploring the role of school-related variables and student demographics. Journal of Multidisciplinary Healthcare, 12, 621.

Sandoval-Hernández, A., & Białowolski, P. (2016). Factors and conditions promoting academic resilience: A TIMSS-based analysis of five Asian education systems. Asia Pacific Education Review, 17(3), 511-520.

Sirin, S. R. (2005). Socioeconomic status and academic achievement: A meta-analytic review of research. Review of Educational Research, 75(3), 417-453.

Thien, L. M., & Ong, M. Y. (2015). Malaysian and Singaporean students’ affective characteristics and mathematics performance: Evidence from PISA 2012. SpringerPlus, 4(1), 563.





