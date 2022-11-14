# FIS_Phase_3_Project
1st Predictive Modeling Project for Flatiron School

https://www.drivendata.org/competitions/66/flu-shot-learning/page/210/

Bull Peter, Slavitt Isaac, Lipstein Greg. 2016. Harnessing the Power of the Crowd to Increase Capacity for Data 
    Science in the Social Sector. Presented at 2016 ICML Workshop on #Data4Good: Machine Learning in Social 
    Good Applications, New York, NY. https://doi.org/10.48550/arXiv.1606.07781


Workflow Outline for Modeling:

Data: DHHS 2009 Flu Vaccine Survey
    -->
    ETL via Pipeline
        -->
        Random Forest modeling on encoded survey responses
        -->
        Naive Bayes modeling on Demographic information
    -->
    Stack Models to create final aggregate model
    -->
    Perform grid search to fine tune hyperparameters and iterate on initial model
    --> 
    *perform boosting if time allows

Report on final metrics, primarily ROC curve AUC score; additionally accuracy, F1, confusion matrix; possibly precision/recall if relevant