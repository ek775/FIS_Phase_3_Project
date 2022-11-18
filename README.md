# FIS_Phase_3_Project
1st Predictive Modeling Project for Flatiron School

Link to competition on drivendata.org:
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

# Business Problem / Hypothetical Stakeholder

Some public health experts have publicly espoused views that COVID-19 vaccination boosters may be headed for an annual regimen not unlike annual influenza vaccination. If this were to take place, current vaccination rates are far below thresholds for herd immunity. Therefore, public health interventions would be necessary to improve vaccination rates. In order to conduct public health interventions of this type, target populations need to be identified, and machine learning offers a novel way to not only target populations, but potentially to target individuals at a more granular level than possible with more traditional methods. 

With this goal in mind, our hypothetical stakeholder is the Department of Health and Human Services.

# Modeling

The dataset provided for approaching this problem comes from the 2009 H1N1 Influenza Survey. The survey includes over 26,000 responses in the training set provided by drivendata.org, and includes approximately 35 questions covering a range of topics from basic demographics to opinions on vaccine efficacy and safety. The target outcome is a self-reported value indicating whether a respondent received their annual influenza vaccination or not, as well as the H1N1 vaccine. To meet the Flatiron School requirements, only influenza vaccination was used as an outcome in order to limit this problem to a binary classification task.

The initial concept for this model involves the use of aggregate model techniques to create a robust model that will be able to return consistently accurate results. This involved the use of a Random Forest and a Naive Bayes classifier as base estimators to a voting classifier that became our final model. This model was then fine tuned with grid searching to find the optimal hyperparameters for training our model accurately.

# Evaluation

The primary outcome for our model were the Receiver Operator Characteristic (ROC) Area Under the Curve (AUC), Accuracy, and F1 scores. These metrics taken as a whole indicate the accuracy of our predictions, as well as the sensitivity and specificity of our model.

Cross validation scores helped us to measure improvement on each model during the iterative modeling process, and a final unseen test set was used for the final evaluation.

Our final model was severely overfit, however, it performed well on the testing data in the final evaluation, beating the dummy classifier by nearly 20 points in accuracy, and beating our initial model by just shy of 5 points. 

# Discussion

Its worth noting that the model performed better with a lower weight assigned to the Naive Bayes classifier, and may indicate that the Decision Tree model that underpins the Random Forest performs better on this specific dataset despite the principles of the Naive Bayes classifier lending themselves toward high performance on demographic data as represented in this dataset. Further improvements may be possible with the application of boosting methods. 

During exploratory data analysis, a key decision was made to train our model even on the null values due to the nature of how this data was collected. In a survey such as this one, respondents are always allowed to refuse to answer any specific question - traditional human subjects research ethics guidelines require this. Thus, an assumption was made that any question that was refused implies a positive action by the respondent rather than an absence of data, and nulls were therefore imputed as a third category for all features in order to capture any trend that may be present in refusal behavior. Before taking this step, we consulted with the Flatiron School course instructor regarding ethical considerations since we are not the original researchers from the group that collected this data and are not affiliated with the institution that conducted the survey. While we do not believe that any ethical guidelines have been breached, future research ethics guidelines may need to take cases like this one into account, and consider them in future discussion.
