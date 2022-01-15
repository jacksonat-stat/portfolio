+++
author = "Hugo Authors"
title = "VDOT Research Project"
date = "2020-04-30"
description = "Sample article showcasing basic Markdown syntax and formatting for HTML elements."
tags = [
    "cost estimation",
    "regression",

]
categories = [
    "themes",
    "syntax",
]
series = ["Themes Guide"]
aliases = ["migrate-from-jekyl"]
+++

# Virginia Department of Transportation: Phase II - Construction Model
## Executive Summary
#### Prepared by:Rebecca Bergee, Anton Highton-Slater, Andrea Jackson, and Chelsea Mitchell (the Team)

The Virginia Department of Transportation (*VDOT*) is seeking a statistical model that will aid in Phase II of their oversight estimation costs. Phase I of their oversight estimation dealt with constructing a model for Preliminary Engineering (PE) costs. This Phase was completed and a model was built and verified by the previous group of statisticians. Phase II is deconstructed into two models: Rite of Way and Construction. This report is an overview with recommendations for a model to be used for the Construction portion of Phase II, which was estimated independently from the model in Phase I. 

VDOT provided the Team with 1,027 projects to use as historical data in model estimation. Data cleaning and manipulation was conducted on the historical data and an updated dataset containing 702 usable projects was created (*the data*). All analysis of the data was conducted using R Studio and SAS software. After the data was cleaned, the team checked statistical assumptions to ensure model estimation could be done. Since normal errors were not observed, a log-transformation was imposed on the data to satisfy the assumption. After the assumptions were tested, the team tested for any multicollinearity between variables. Results suggested that there was a strong correlation between “*CN.Estimate*” and “*Total.Estimate*” as well as “*CN.Expend*” and  “*Expend.to.be.excluded*”. Per the advice of VDOT, “*Total.Estimate*” and “*Expend.to.be.excluded*” were removed from analysis to rectify multicollinearity. Once assumptional and multicollinearity issues were remedied, the team deployed Forward, Backward, and Stepwise selection as model selection techniques. The resulting model included an intercept and six of the variables: “*FEDERAL_HIGHWAY_DESC*”, “*ROADWAY_OWNERSHIP*”, “*CN.Expend*”, “*X..VDOT.Cost..CN.*”, “*District*”, and “*ENVIRONMENTAL_WORK_DESC*”.



### Virginia Department of Transportation: Phase II - Construction Model
#### Technical Report
#### Prepared by: Rebecca Bergee, Anton Highton-Slater, Andrea Jackson, and Chelsea Mitchell (the Team)


1. Data Cleaning & Manipulation

Data Cleaning Files
*	CN_Projects.xlsx
* AdditionalData_VCU_03302020_v1.xlsx
*	Convert.xlsx.to.csv.R
*	CN_Projects.csv
*	AdditionalData_VCU_03302020_v1.csv
*	VDOT_Data_Cleaning.R
*	Clean.CN.Data.csv

Files “CN_Projects.xlsx” and “AdditionalData_VCU_03302020_v1.xlsx” were imported into R Studio to be converted into csv files. Using the “xlsx” package, the file titled “Convert.xlsx.to.csv.R” rewrites the excel files to csv files. Then, the csv files were loaded into R Studio and cleaned by the file titled “VDOT_Data_Cleaning.R”. The two datasets were combined into one. As requested by VDOT, the following UPCs were removed based on $0 in oversight expenditures, work performed as a service, or if an agreement cannot be located to verify inclusion into the dataset. 

* 104764
* 104766
* 93135
* 104166
* 104167
* 104061
* 107151
* 80431

Specific columns were then removed from the dataset that were not needed for statistical analysis including the “X”, “UPC”, and “DESCRIPTION” columns. As requested by VDOT, “PE_START_DATE”, “PE_END_DATE”, “RW_START_DATE”, “RW_END_DATE”, “CN_START_DATE”, “CN_END_DATE”, “PE.Estimate” and “RW.Estimate” were also removed. 

 ### Binary Variables
*	FEDERAL_ELIGIBILITY_DESC
*	FEDERAL_HIGHWAY_DESC
*	ROADWAY_OWNERSHIP
*	JURISDICTION_DESC

 Federal eligibility was classified as either federally or not federally eligible. The federal highways were classified as either NHS or NON NHS. The roadway ownership was classified as either locally or state owned. Specific jurisdictions were classified as UCI according to VDOT allowing a binary classification of either UCI or Not UCI. 

### Quantitative Variables
*	VDOT.Cost
*	VDOT.Cost..CN
*	CN.Estimate
*	Total.Estimate
*	CN.Expend
*	Expend.to.be.excluded

	The section on quantitative variables in the script removes any symbols from the data and redefines each entry as numerical to ensure proper data recognition. 

Categorical Variables
*	SCOPE_OF_WORK_DESC
*	District
*	ENVIRONMENTAL_WORK_DESC 

	Scope of work has 24 categories implying the need for 23 indicator variables. The 23 indicators were created for scope of work using all categories except “Utilities” labeled as Scope1, … , Scope23. There are 10 districts, so 9 indicator variables were created using all districts except “Staunton” labeled as District1, … , District9. Notice here that we kept all of the districts included in the data as indicator variables. Whereas, the Phase I team created a binary variable for “District.” The results will vary based on this difference in classification. In the environmental work column, the missing data was replaced with zeros. Of the 6 categories, all categories except “0” were turned into indicator variables labeled as ENVR1, … , ENVR5. 
	At the end of the script, all cost entries with “0” were removed. All project status entries with “CANCELED” or “0” were removed. Then, all missing data that has not been corrected earlier in the script is omitted. Once the data was cleaned, any remaining columns that were unnecessary for analysis were removed. The final dataset was exported as a csv file titled “Clean.CN.Data.csv” prepared for statistical analysis. The original data and cleaned data share the same column names to avoid confusion. “Clean.CN.Data.csv” was created solely for the VCU interns to analyze. 

### 2. Assumptions

#### *2.1 Normality and Homoscedasticity*

Linear regression requires independent normally distributed errors with a mean of zero and a constant variance. We checked the normality of the residuals of the original data by plotting the “Residual vs Fitted” and “Normal Q-Q” plots using the R Studio software. We also checked these assumptions with the same plots in SAS. 

### **R Output**

![R output1]( /images/vdot-resid-plot.png)

![R output2](/images/vdot-qqplot.png)

Notice that the residuals appear to have a mean of zero but inconsistent variance. Also, the normality is questionable based on the Normal plots. This implies the need for a transformation. When correcting for homoscedasticity, the response variable needs to be transformed. We chose to scale the response using a log-transformation. After taking the log of the “VDOT.Cost” variable, the normality assumptions were corrected as demonstrated by the new plots.   
### **R Output**

![R output3]( /images/vdot-transform-resid-plot.png)

![R output4](/images/vdot-transform-qqplot.png)


Notice that the residuals have a more consistent variance when plotting the residuals against the predicted values and an improved linear fit according to the normal plots. 

2.2 *Multicollinearity*

After correcting the normality of the errors, we also checked for multicollinearity. Starting with our code in R Studio, we used the correlation matrix to find that the “CN.Estimate” and “Total.Estimate” variables had a 98.2% correlation, while the “CN.Expend” and “Expend.to.be.excluded” variables were 99.9% correlated. Using SAS, we verified these correlations by plotting each relationship.

These relationships indicate that one variable from each correlated pair needs to be removed from the analysis. After consulting VDOT, it was decided that “Total.Estimate” and “Expend.to.be.excluded” should be removed. Now that the multicollinearity and normality assumptions are satisfied, the data is deemed ready for analysis.  

### 3. Model Selection

The goal of this project is to develop a robust model that predicts the construction costs for VDOT. In order to build a regression model, various model selection methods can be implemented. We focus on Forward, Backward, and Stepwise selection to help determine the best model. All three techniques begin with a full model containing all variables. In this case, the full model is given as follows 



where  are the predicted values of the full model and   is a matrix of the coefficient estimates. Using the full model, we ran forward selection first. Forward model selection returned the full model suggesting that all variables were significant. This proved to be true for both the SAS and R Studio output. However, Backward and Stepwise selection resulted in a different model. 
Backward and Stepwise selection both agreed upon a more concise model. Both methods indicated that “FEDERAL_HIGHWAY_DESC”, “ROADWAY_OWNERSHIP”, “CN.Expend”, “X..VDOT.Cost..CN”, “District”, and “ENVIRONMENTAL_WORK_DESC” were significant variables to be included in the model. As stated in the Data Cleaning section, categorical variables require that all categories or no categories be added into the model. In this process, we chose to include all Districts and classifications of Environmental Work. Thus, all districts are significant, whereas in Phase I only a specific district was deemed significant. 
Backward and Stepwise selection resulted in the following model



where  are the predicted values of the reduced model and b is a matrix of the coefficient estimates. We analyzed the full (y1) and reduced (y2) models. The full model predicts with 45.97% accuracy based on the Adjusted R-Square value provided by the R Studio analysis. The reduced model (y2) predicts with 45.38% accuracy based on the same analysis. Though there is a slight decrease in accuracy, the prediction capability barely change when running the more concise model. Hence, we chose to keep the reduced model since not all variables contribute to the overall model performance. We advise that VDOT use model y2 as a preliminary model in need of validation.

### 4. Preliminary Model

As stated in the Model Selection section of this report, we advise that VDOT use the following model



where  are the predicted values of the model and b are the coefficients estimates. The following table gives the variables included in the regression model with the corresponding estimates. 



Variable             |	Estimate (b)
---------            |--------------
(Intercept)          |	7.010e+00
FEDERAL_HIGHWAY_DESC |		3.606e-07
ROADWAY_OWNERSHIP    |		-4.831e+00
CN.Expend            |		4.006e-07
X..VDOT.Cost..CN.    |		3.686e+00
District1	           |	 1.213e+00
District2	           |	1.957e-01
District3 |	1.450e-01
District4	|	1.115e+00
District5	|	8.649e-01
District6	|	1.280e+00
District7	|	1.362e+00
District8	|	-5.340e-01
District9	|	1.437e+00
ENVR1	|	2.062e-01
ENVR2	|	-1.004e+00
ENVR3	|	9.390e-01
ENVR4	|	5.127e-01
ENVR5	|	-2.267e+00





### 5. Conclusion
The team was tasked to estimate a model to predict VDOT oversight costs for the Construction portion of Phase II. Data cleaning of the provided data was completed in conjunction with VDOT recommendations, followed by testing of assumptions and a check for multicollinearity. We were able to construct a preliminary model that yielded a favorable fit containing the following variables: “FEDERAL_HIGHWAY_DESC”, “ROADWAY_OWNERSHIP”, “CN.Expend”, “X..VDOT.Cost..CN.”, “District”, and “ENVRIONMETNAL_WORK_DESC”. Although we believe that this model is appropriate for estimating Construction oversight costs, we recommend model validation be run to ensure its efficacy. 



