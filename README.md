# 1. Data Description

## Players Dataset
- Observations: 196 | Variables: 7  
- Summary (played_hours): min = 0, max = 223.1, mean = 5.81  
- Summary (Age): min = 9, max = 58, mean = 21.14  

**Variables:**  
- experience (qualitative) – skill level  
- subscribe (qualitative) – newsletter subscription status  
- hashedEmail (qualitative) – anonymized email  
- played_hours (quantitative) – hours played  
- name (qualitative) – gamer name  
- gender (qualitative) – identified sex  
- Age (quantitative) – years lived  

**Issues:**  
- "played_hours" lacks a defined timeframe; responses may be inconsistent.  
- Skill level classifications may not match hours played, which could affect modeling credibility.

---

## Sessions Dataset
- Observations: 1535 | Variables: 5  
- Summary (original_start_time): min = 1.7124e+12, max = 1.72733e+12, mean = 1.7192e+12  
- Summary (original_end_time): min = 1.7124e+12, max = 1.72734e+12, mean = 1.7192e+12  

**Variables:**  
- hashedEmail (qualitative) – anonymized email  
- start_time / end_time (quantitative) – session start and end  
- original_start_time / original_end_time (quantitative) – likely converted to seconds  

**Issues:**  
- Units for original_start_time and original_end_time are unclear.  
- Only the difference between start and end times is meaningful, requiring additional processing.

# 2. Questions

**Broad:** What player characteristics and behaviours predict subscribing to a game-related newsletter, and how do these vary by player type?  
**Specific:** Does the amount of time a player spends on video games correlate with subscription status?

# 4. Methods and Plan

To address the questions, each explanatory variable will be compared individually with the response variable (subscribe).  
- Visualize each variable against the response to identify potential associations.  
- Qualitative variables: use chi-square tests; lower p-values indicate stronger predictors.  
- Quantitative variables: use K-NN; evaluate RMSPE for prediction accuracy.  
- Data will be split into training (70%), validation (10%), and testing (20%) sets, with cross-validation to improve reliability.  
- Additional visualizations will assess relationships among explanatory variables.  

This approach is appropriate because it directly addresses the research questions using simple, well-established methods. Assumptions include truthful responses and sufficient data size. A limitation is the reliance on visualizations, which may introduce subjectivity in interpretation.


