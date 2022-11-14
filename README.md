# FIS_Phase_3_Project
1st Predictive Modeling Project for Flatiron School

https://www.drivendata.org/competitions/66/flu-shot-learning/page/210/

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