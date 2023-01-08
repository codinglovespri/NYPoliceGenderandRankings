# NY Police Gender and Rankings

## Summary of Findings    

### ⭐ Introduction ⭐    
This dataset contains 12,000 complaints filed by NY civilians against police officers. The columns of the dataset contain data about the police officers as well as the complainants. The question I investigate is does the police officers' gender influence whether a police gets demoted after the incident?

### ⭐ Cleaning & Handling Missingness ⭐   
To clean the data, I created a helper function to replace the "Unknowns" into np.NaN. I also created a dictionary that represented the MOS rankings in integer form. Then, I created another helper function to replace the MOS rankings with the integers according to the dictionary for easier comparison later on. Finally, I imputed the missing values in the dataset using probabilistic imputation to generate a more accurate dataset.

### ⭐ EDA ⭐   
I plotted several variables against each other. The main takaways include a rise in complaints throughout the years 2000 and 2018, with a drop in 2020 (probably due to Covid).

### ⭐ Hypothesis Testing ⭐    
H0: NY Police officers are no less likely to be demoted if they identify as Male.

H1: NY Police officers are more likely to be demoted if they identify as Male.

For the test statistic, I decided to use mean difference of rank. To clarify, the difference in rank is the rank_now substracted by the rank_incident. To calculate this, I shuffled the complainant_ethnicity column and retrieved mean difference of rank for the Male and non Male complainants. Then, I put each test statistic in a list and counted how many were larger than our observed test statistic of 0.0953. As for the significance value, I decided to use .05. After running the simulations 800 times, I got a p-value of .0075. Since .0075 < .05, the conclusion rejects the null hypothesis that NY Police officers are no less likely to be demoted if they identify as Male.

