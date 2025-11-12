# 1. Data Description

## Summary of Players Dataset
- #observations : 196  
- #variables : 7  
- #Summary statistics in order for played_hours variable (min, max, mean) : 0, 223.1, 5.81  
- #Summary statistics in order for Age variable (min, max, mean) : 9, 58, 21.14  

### List of Each Variable and Classification (left -> right):
- experience = qualitative  
- subscribe = qualitative  
- hashedEmail = qualitative  
- played_hours = quantitative  
- name = qualitative  
- gender = qualitative  
- Age = quantitative  

### Variable Meaning:
- experience = this variable describes the level of skill to which a gamer can perform  
- subscribe = this variable defines whether a gamer is registered for a subscription to a gaming newsletter
- hashedEmail = an email address transformed to protect personal information  
- played_hours = the number of hours played in a given time frame  
- name = the gamers inputed name  
- gender = the sex to which a gamer identifies  
- Age = number of years lived inputed as a whole number (discrete numerical data)  

### Issues with the Players Dataset:
- The numerical variable "played_hours" does not have a defined domain to which the hours were recorded for the reader of a dataset. Therefore, I am not sure if these hours are taken from day timeframe, or greater/less than that. In addition, if that was not explicit to the gamers who filled out the form, their numerical hours could be skewed in reference to each other, making any calculation invalid.  

### Potential Issues with the Players Dataset:
- I noticed that the classification of skill level is inconsistent with the number of hours recorded for an observation. For example, a gamer classified as a pro with a very minimal magnitude (or even zero) for their hours of gameplay. (See table above) This could affect the model that will be built later in the project because they might not be related logically, which can offset the model and its predictions and also loose the credibility of the data initially recorded.  

---

## Summary of Sessions Dataset
- #observations : 1535  
- #variables : 5  
- #Summary statistics in order for original_start_time variable (min, max, mean) : 1.7124e+12, 1.72733e+12, 1.7192e+12  
- #Summary statistics in order for original_end_time (min, max, mean) : 1.7124e+12, 1.72734e+12, 1.7192e+12  

### List of Each Variable and Classification (left -> right):
- hashedEmail = qualitative  
- start_time = quantitative  
- end_time = quantitative  
- original_start_time = quantitative  
- original_end_time = quantitative  

### Variable Meaning:
- hashedEmail = an email address transformed to protect personal information  
- start_time = the date, hour, and minute at which the gamers session started  
- end_time = the date, hour, and minute at which the gamer ended their session  
- original_start_time = the variable start_time converted to one unit, most likely as seconds since it is a very large number  
- original_end_time = the variable end_time converted to one unit, most likely as seconds since it is a very large number  

### Issues with the Sessions Dataset:
- the orignial_start_time and original_end_time variables are not defined in their units or set domain of time either, leaving the reader to guess what these numerical values even mean.  

### Potential Issues with the Sessions Dataset:
- The starting time and ending time variables do not mean anything on their own, it is the difference that has relevance to the study being performed. Therefore, the difference will need to be calculated, elimating both of those columns and adding a new one which will take extra work.

## 2. Questions

### Broad Question
- What player characteristics and behaviours are most predictive of subscribing to a game-related newsletter, and how do these features differ between various player types?

### Specific Question
- Does the amount of time a player spends on video games have a correlation to their subscription status?

  ## 4. Methods and Plan

A method that could be used to address the main question of this study is to perform tests comparing each explanatory variable in the dataset individually with the response variable in question: subscription to a game-related newsletter. 
First, the response variable will be visualized against each explanatory variable separately to assess whether any show signs of correlation. For any qualitative variables that appear to do so, a chi-square test of independence will be performed. To compare which variable is most predictive, the p-values will be examined, where a lower magnitude indicates a better predictor. 
For the quantitative explanatory variable, a K-NN test will be performed, and the RMSPE will be evaluated. Discretion will be used to determine whether the RMSPE value is acceptable relative to the values in the dataset. 
In addition, explanatory variables will be compared to each other using additional visualizations to determine whether those traits are related as well.


A method that could be used to address the main question of this study is to perform tests comparing each explanatory variable in the data set individually with the response variable in question: subscription to a game-related newsletter. First, visualize the response variable against each explanatory variable separately to assess whether any have an appearance of correlation. For any qualitative variables that show potential association, a chi-square test of independence will be performed. To compare which one is most predictive, we look at the p-values, where the lowest magnitude indicates a better predictor variable. For the quantitative explanatory variable, a K-NN test will be performed, and the RMSPE will be evaluated. Discretion will be used to determine if the RMSPE value is acceptable relative to the numbers in the data set. The K-NN test will follow the procedure of the demonstrations applied in lecture. It will be split into a training, validation, and testing set, with 70% of the data used for training, 10% for validation, and 20% for testing, immediately after reading the initial data frame. Cross-validation will also be used to increase the probability of an accurate model. In addition, explanatory variables will be compared to each other using extra visualizations to determine whether those traits have a relation to each other as well.  

This method is appropriate because it addresses the questions proposed directly with relatively simple tests that have been taught in this class or other classes previously. To accept the results from this method, the results from each observation need to be assumed to be truthful and serious responses, which may not always hold when opening a form to a public pool. In addition, the size of the data frame needs to be accepted as large enough in observations to propose any predictive measurements. A weakness of this method is that it focuses heavily on visualizations to make conclusions, which can be subject to subjective interpretations.


