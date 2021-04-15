# **The importance of personality traits in predicting school progression problems in Brazil**







## Table of Contents

1.Getting Started

  - [Resumo]()
  - [Importância do trabalho]()
  - [Objetivos do projeto]()
  - [Etapas concluidas e a concluir]()

2.[Notebooks e Arquivos]()

3.[Modelos Usados]()

4.[Description of variables]()

  - Personality Traits
    - id
    - grade_2012
    - grade_2017
    - month, year, semester
    - school_2012
    - ethinicity
    - gender
    - failed_before_2012
    - mother_educ
    - pre_k_pub, pre_k_priv, kinder_pub, kinder_priv
    - lang_2012, math_2012
  - Non personality traits
    - act_2012
    - aes_2012
    - alt_2012
    - anx_2012
    - ass_2012
    - cmp_2012
    - dep_2012
    - ids_2012
    - ord_2012
    - sfd_2012

## Summary

Neste projeto, utilizaremos uma rica base de dados de alunos da rede escolar da cidade de Sertãozinho (SP). Temos informações para uma coorte de quase 2000 alunos nos anos de 2012 e 2017, sendo possível saber quais alunos atrasaram entre os dois anos. Para predizer quais alunos não progrediram cinco anos escolares entre 2012 e 2017, utilizaremos informações dos alunos em 2012, tais como: educação dos pais, traços de personalidade, notas, indicadores de pobreza, entre outras. Nosso objetivo principal é entender qual o poder preditivo dos traços de personalidade. Para isso faremos análises utilizando três conjuntos diferentes de features: (i) somente traços de personalidade, (ii) todas as features excluindo traços de personalidade e (iii) conjunto completo de features. Além de comparar os três tipos de análise, também utilizaremos ferramentas de explicação para entender melhor nossos classificadores caixa-preta.

In this project we used a rich dataset of the schooling system in Sertãozinho (in the countryside of the state of São Paulo, Brazil). We have information for a cohort of about 2000 students between 2012 and 2017, being able to tell which students failed at least a grade between these years. To predict which students didn't pass all five years between 2012 and 2017, it was used information collected in 2012 such as: Parents' education, personality traits, grades, poverty indicators and others. Our main goal is to understand the predictive power of personality traits. For that, we analysed using 3 different group of features: (i) Only personality traits, (ii) All features excluding personality traits, and (iii) All features. Besides comparing the analysis done in each feature group, we used tools for explaining our black box classifiers.



  
  
  
  







## Built With


## Getting Started
## Goals of this project
## What has been done


## Description of variables


## id

Description: An unique number that characterize a single individual of the survey. Some ids are missing, probably people who were excluded from the survey by some criteria.

It is a discrete variable.

its factors: numbers between 1 and 5311






## grade_2012
Description: which grade the student was in 2012

It is a discrete variable.

its factors: 4, 5 or 6




## grade_2017
description: Which grade the student was in 2017

It is a discrete variable.

its factors: 7, 8, 9, 10, 11, 12


## month, year, semester
Description: Year and month of the student's birth

It is a discrete variable.




## school_2012
Description: A student's school category, so it tells whether It's a private school, state school or municipal school. For context, in Brazil, private schools are usually associated with better education in comparison to the other two.


It's possible values: 'municipal', or 'estadual', or 'privada'
Which means, respectively: municipal, state, private

It is a discrete variable.



## ethinicity
Description: the student's ethinicity

Categoric

It's factors: 'parda', 'branca', 'preta', 'indigena', 'amarela' 

Which means, respectively: 'brown', 'white', 'black', 'indigenous' , 'yellow'.

It is a discrete variable.



## gender
Description: The student's gender\

Categoric

It's factors: 'homem', 'mulher' 

Which translated means, respectively: 'male', 'female'

It is a discrete variable.



## failed_before_2012

Description: if the student has already failed before the year of 2012 


It's factors: 'sim',or 'nao'

Which translated means, respectively: 'yes','no' 

It is a discrete variable.


## mother_educ
Description: student mother's school degree

Categoric

It's factors: 'nunca_estudou', or 'ef1', or 'ef2', or 'em', 'superior', or 'nao_sabe' 

Which translated means, respectively: 
ef1 = 'Ensino fundamental 1' = It means if the person left school at the expected time, the person left school at 10 years old. 

ef2 = 'Ensino fundamental 2' = It means if the person left school at the expected time, the person left school at 14 years old. 

em = 'Ensino médio' = High school,composed of 3 school years, expected that the person studies between 14 and 17 years old. So if the left school at 17 years old.

superior = 'Ensino Superior' = It means the person has finished a university degree. 

nao_sabe = 'Não sabe' = It means the person that was interviewed doesn't know. 

It is a discrete variable.




## pre_k_pub, pre_k_priv, kinder_pub, kinder_priv
Description:

pre_k_pub: if the student used to frequent a public pre-kindergarden  

pre_k_priv: if the student used to frequent a private pre-kindergarden 

kinder_pub: if the student used to frequent a public kindergarden 

kinder_priv: if the student used to frequent a private kindergarden 


It's factors: sim, nao 

Which translated means, respectively: 'yes','no' 

It is a discrete variable. 

## lang_2012, math_2012
description: : The tests scores were standardized to have null mean and unit standard deviation in 2012 among those students who form our actual sample; 

It is a continuous variable.




## act_2012

description: describes the propension to engage in energetic behaviour 

It is a continuous variable.


## aes_2012
Aesthetics 

Description: Describes the propension to have sensibility to art.High scorers can be described as those who value aesthetic experiences and who are moved by art 
and beauty. On the other hand, low scorers can be described as insensitive to art and unappreciative of beauty; 


It is a continuous variable. 




## alt_2012
Altruism  

Description: High scorers can be described as warm, softhearted, gentle, generous, and kind. On the other hand, 

low scorers can be described as selfish, cynical, cold, and snobbish; 


It is a continuous variable.



## anx_2012
Anxiety 

Description: High scorers can be described as apprehensive, fearful, prone to worry, nervous and tense. On the other hand, low scorers can be described as calm, relaxed, stable, fearless.

It is a continuous variable.




## ass_2012
Assertiveness

Description: High scorers can be described as dominant, forceful, confident, and decisive. On the other hand, low scorers can be described as unassuming, retiring, and reticent.

It is a continuous variable.



## cmp_2012
Compliance

Description: High scorers can be described as deferential, obliging, and kind. On the other hand, low scorers can be described as stubborn, demanding, headstrong, and hardhearted.

It is a continuous variable.



## dep_2012
Depression

description: High scorers can be described as prone to feelings of guilt, sadness, hopelessness, and loneliness. On the other hand, low scorers can be described as being seldom sad, hopeful, confident, and as feeling worthwhile; (copied from the paper)

It is a continuous variable.



## ids_2012
Ideas

description: High scorers can be described as intellectually curious, analytical, and theoretically oriented. On the other hand, low scorers can be described as pragmatic, factually oriented, and unappreciative of intellectual challenges; (copied from the paper)

It is a continuous variable.



## ord_2012
Order

description: High scorers can be described as precise, efficient, and methodical. On the other hand, low scorers can be described as disorderly, impulsive, and careless; (copied from the paper)

It is a continuous variable.



## sfd_2012
Self-Discipline

description: High scorers can be described as organized, thorough, energetic, capable, and efficient. On the other hand, low scorers can be described as unambitious, forgetful, and absent-minded; (copied from the paper)

It is a continuous variable.






To do:

- [X] Create links within this document([look up the documentation](https://docs.github.com/en/github/writing-on-github/basic-writing-and-formatting-syntax#lists))







