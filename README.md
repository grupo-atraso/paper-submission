# **The importance of personality traits in predicting school progression problems in Brazil**







## Table of Contents

1.[Summary](https://github.com/grupo-atraso/paper-submission/blob/main/README.md#summary)


2.[Main results]()




3.[Description of notebooks]()
  
  


4.[Description of variables]()

  - [Non personality Traits]()
    
  - [Personality traits]()
    

## Summary


In this project we used a rich dataset of the school system in Sertãozinho (in the countryside of the state of São Paulo - Brazil). We have data for a cohort of about 2000 students gathered in 2012 and 2017, being able to tell which students repeated at least one grade between these years. To predict which students didn't progress all five years between 2012 and 2017, it was used information collected in 2012 such as: Parents' education, personality traits, grades, poverty indicators and others. Our main goal is to understand the predictive power of personality traits. For that, we analysed using 3 different group of features: (i) Only personality traits, (ii) All features excluding personality traits, and (iii) All features. Besides comparing the analysis done in each feature group, we used tools for explaining our black box classifiers.



  

## Main results

![image](https://user-images.githubusercontent.com/82613797/115277315-81924300-a11a-11eb-897b-e5a780bfb42b.png)

SUVREL relevance analysis (function relevanceplot). It displays the relevance score for each feature in distance calculation.

![image](https://user-images.githubusercontent.com/82613797/115277579-d5049100-a11a-11eb-927c-1c5a934835f0.png)
 
Barplots of average cross-validation AUCs (±std. error) with K= 10. We combined three sets of features (Personalities only,  Others Only and All features) and two models (Logistic Regression and XGBoost Classifier).  The red line displays the maximum average ROC AUC score achieved.


  ## Description of notebooks
  
   - CrossValidation
   
      Here we run our Logistic regression and XGBoost models, and compare their performances.
   
   - DataDescription
   
      In this notebook we describe basic informations about each variable, such as: Variable name, variable description, whether the variable is discrete or continuous, if the variable is continuous, the components that describe it (min, 25%, 50%, 75%, max, mean, number of terms), if the variable is discrete, we list its factors, we show the percentage of NAs, and we present histograms of the variables' factors when appropriate.

   - DataSummarization

      In this notebook we run correlation tests between variables, show heatmaps, boxplots, apply dimentional reduction, MDS plot, linear discrimination analysis and Supervisoned Variational Relevance Learning (SUVREL).
 
   - EditingDataset

      In this notebook we execute some data cleaning and preparation. We created the variable 'semester', added the variable 'delay' and 'delay years' as dummy variables, converted variables that had factors as text into dummy variables when appropriate, and performed data processing techiniques to make numerical variables have average = 0 and standard deviation = 1.









## Description of variables

In the article we define three distinct feature groups: Personality traits, Non personality traits (which in the paper is also referred as "Other features" or "Others only") and All features (Personality traits and Non personality traits combined).

## Non personality traits

  - id

    Description: An unique number that characterize a single individual of the survey. Some ids are missing, probably people who were excluded from the survey by some criteria.

    It is a discrete variable.

    Its factors: numbers between 1 and 5311






   - grade_2012
   
      Description: which grade the student was in 2012

      It is a discrete variable.

      Its factors: 4, 5 or 6




   - grade_2017
    
        description: Which grade the student was in 2017

        It is a discrete variable.

        Its factors: 7, 8, 9, 10, 11, 12


   - month, year, semester
    
        Description: Month: Month of the student's birth. Inputs range from 1 to 12, indicating each month of the year. 
        
        Year: Year of the students' birth. Inputs are in the format 'YYYY' e.g. '1999'.
        
        Semester: Tells which semester the student was born. Inputs are either 1 or 2, indicating that the student was born on the first semester of the year or the second, respectively.

        They are discrete variables.




   - school_2012
     
        Description: A student's school category, so it tells whether It's a private school, state school or municipal school. For context, in Brazil, private schools are               usually associated with better education in comparison to the other two.


        It's possible values: 'municipal', or 'estadual', or 'privada'
        Which means, respectively: municipal, state, private

        It is a discrete variable.



   - ethinicity
     
        Description: the student's ethinicity

        Categoric

        It's factors: 'parda', 'branca', 'preta', 'indigena', 'amarela' 

        Which means, respectively: 'brown', 'white', 'black', 'indigenous' , 'yellow'.

        It is a discrete variable.



   - gender
     
        Description: The student's gender.

    

        It's factors: 'homem', 'mulher' 

        Which translated means, respectively: 'male', 'female'

        It is a discrete variable.



   - failed_before_2012

        Description: if the student has already repeated a grade before the year of 2012 .


        It's factors: 'sim',or 'nao'

        Which translated means, respectively: 'yes','no' 

        It is a discrete variable.


   - mother_educ
     
        Description: student mother's school degree

        

        It's factors: 'nunca_estudou', or 'ef1', or 'ef2', or 'em', or 'superior', or 'nao_sabe' 
  
        Which translated means, respectively: 
        ef1 = 'Ensino fundamental 1' = It means that if the mother attended each grade at the ideal time, the mother left school at some point between 10 and 14 years old. 

        ef2 = 'Ensino fundamental 2' = It means that if the mother attended each grade at the ideal time, the mother left school at some point between 14 and 17 years old. 

        em = 'Ensino médio' = High school, composed of 3 school years, It's expected that the person studies it between 14 and 17 years old. So the mother left school at 17 years old and didn't pursue further education.

        superior = 'Ensino Superior' = It means the mother has finished a university degree. 

        nao_sabe = 'Não sabe' = It means that the person who was interviewed doesn't know about their mother's education. 

        It is a discrete variable.




   - pre_k_pub, pre_k_priv, kinder_pub, kinder_priv
     
        Description:

        pre_k_pub: if the student used to frequent a public pre-kindergarden  

        pre_k_priv: if the student used to frequent a private pre-kindergarden 

        kinder_pub: if the student used to frequent a public kindergarden 

        kinder_priv: if the student used to frequent a private kindergarden 


        It's factors: sim, nao 

        Which translated means, respectively: 'yes','no' 

        It is a discrete variable. 

   - lang_2012, math_2012
     
        Description: The tests scores were standardized to have null mean and unit standard deviation in 2012 among those students who form our actual sample.
        
        lang_2012: Language test taken in 2012
        
        math_2012: Math test taken in 2012

        It is a continuous variable.
        
   - delay
   
      Description: It tells whether the student has repeated at least one grade in school.
      It's factors: 0 (so the student never repeated a grade in school) or 1 (the student repeated at least one grade in school).
      
      It is a discrete variable.
   
   - delay_years 

      Descrption: It tells how many grades the student has repeated.
      
      It is a discrete variable.

## Personality traits


   - act_2012

        Activity
        
        description: describes the propension to engage in energetic behaviour 

        It is a continuous variable.


   - aes_2012
     
        Aesthetics 

        Description: Describes the propension to have sensibility to art.High scorers can be described as those who value aesthetic experiences and who are moved by art 
        and beauty. On the other hand, low scorers can be described as insensitive to art and unappreciative of beauty. 


        It is a continuous variable. 




   - alt_2012
     
        Altruism  

        Description: High scorers can be described as warm, softhearted, gentle, generous, and kind. On the other hand, 

        low scorers can be described as selfish, cynical, cold, and snobbish.


        It is a continuous variable.



   - anx_2012
     
        Anxiety 

        Description: High scorers can be described as apprehensive, fearful, prone to worry, nervous and tense. On the other hand, low scorers can be described as calm, relaxed,         stable, fearless.

        It is a continuous variable.




   - ass_2012
     
        Assertiveness

        Description: High scorers can be described as dominant, forceful, confident, and decisive. On the other hand, low scorers can be described as unassuming, retiring, and           reticent.

        It is a continuous variable.



   - cmp_2012
     
        Compliance

        Description: High scorers can be described as deferential, obliging, and kind. On the other hand, low scorers can be described as stubborn, demanding, headstrong, and hardhearted.

        It is a continuous variable.



   - dep_2012
     
        Depression

        Description: High scorers can be described as prone to feelings of guilt, sadness, hopelessness, and loneliness. On the other hand, low scorers can be described as being         seldom sad, hopeful, confident, and as feeling worthwhile.

        It is a continuous variable.



   - ids_2012
     
        Ideas

        Description: High scorers can be described as intellectually curious, analytical, and theoretically oriented. On the other hand, low scorers can be described as                 pragmatic, factually oriented, and unappreciative of intellectual challenges.

        It is a continuous variable.



   - ord_2012
     
        Order

        description: High scorers can be described as precise, efficient, and methodical. On the other hand, low scorers can be described as disorderly, impulsive, and careless.

        It is a continuous variable.



   - sfd_2012
     
        Self-Discipline

        description: High scorers can be described as organized, thorough, energetic, capable, and efficient. On the other hand, low scorers can be described as unambitious,             forgetful, and absent-minded.

        It is a continuous variable.














