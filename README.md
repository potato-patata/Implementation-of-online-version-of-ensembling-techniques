# Implementation of online version of ensembling techniques
My main motive for trying to implement this technique as compared to other options was to classify streaming data or online data effectively without the need for storing the entire dataset and to produce similar results as compared to their batch counterparts.
I performed experiments on two datasets ‘car’ and ‘nursery’. Car data has 1728 instances and 6 inputs and 1 target variable. Nursery dataset has 12960 number of instances with 8 inputs and 1 target variable. Data was split as 70% for training dataset and 30% for testing dataset.
Algorithm steps:
1. Process each training instance on arrival without need of storing and pre-processing
2. Online bagging trains its ‘M’ base model by creating ‘K’ copies (K is Poisson random variable) of the new instances which arrive and send it to all ‘M’ base models for training.
3. Repeat above two steps 'K' times and train the base model on this.
4. For new instances coming let base models classify based on Poisson weight, if it classifies correctly then update its weight according to properly classified observations, else update its weight with adding error finally return sum of results of base models for increasing training efficiency.
Results achieved: (Online bagging with naive Bayes as base classifier)
Accuracy for car dataset: 67.34%
Accuracy for nursery dataset: 84.637%
