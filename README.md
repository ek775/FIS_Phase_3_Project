# FIS_Phase_3_Project
1st Predictive Modeling Project for Flatiron School

https://www.drivendata.org/competitions/66/flu-shot-learning/page/210/

Bull Peter, Slavitt Isaac, Lipstein Greg. 2016. Harnessing the Power of the Crowd to Increase Capacity for Data 
    Science in the Social Sector. Presented at 2016 ICML Workshop on #Data4Good: Machine Learning in Social 
    Good Applications, New York, NY. https://doi.org/10.48550/arXiv.1606.07781


# Workflow Overview for Modeling:

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

# Business Data and Understanding

For our project, we are looking at seasonal vaccine data. We are using this data to predict future vaccination statistics.

Our stakeholder audience is the Department of Health and Human Services.

# Modeling

We are using a random tree forest and a naive baysian model to predict the statistic behavior.

# Evalutation

We ran our models through a grid search. This grid search looked through different hyper parameter options and returned our the best model accoridng to its computations.

The data for these models was also ran through a pipeline before going into the grid search.

# Conclusion

Our model concludes that we can predict if our target will get vaccinated with a 79% accuracy.