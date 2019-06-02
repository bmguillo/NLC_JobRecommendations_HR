# Watson Natural Language Classifier

## Definition of Text Classification
- It is an area of AI which is natural language processing (NLP) that focuses on labeling and organizing text

## Purpose of the Service:  
- It is to quickly train custom machine learning models to analyze and label(categorize, sort or classify) your textual data in order to identify next best actions, organize your data, or analyze your data for trends and new insights. This saves a tremendous amount of time.

## Various Usecases
- Job recommendations e.g. creative, technical, sales(this github example)
- Analysis of AirBnb Reviews e.g. good, bad, neutral
- Classify programming languages
- Classify spam
- sort posts on a message board 
- classify weather data e.g. conditions, temperature
- support tickets

## Using Data Science Methodology

1. Business Understanding(Identify Business Problem) - As an HR professional, I want an easy way to identify or label candidates that have certain qualities for specific job types based on those qualities
2. Choosing the Right Algorithm - In this case, its classification. We are using Natural Language Classifier
3. Data Requirements - Resume data & job role data, using sample with classifiers for training data
4. Data Science Tools - structured data(excel) & Python
5. Locate data - job repository & resume repository
6. Training & Testing Classifier(steps below)

## Process to train/test a classifier in Watson Natural Language Classifier: 


Prerequisites
- IBM Cloud account: If you do not have an IBM Cloud account, you can create an account [here](https://cloud.ibm.com/)
- Basic knowledge of Watson Natural Language Classifier by viewing [docs](https://cloud.ibm.com/docs/services/natural-language-classifier?topic=natural-language-classifier-natural-language-classifier&cm_mc_uid=08582511162115581306652&cm_mc_sid_50200000=48334731559443154666&cm_mc_sid_52640000=20154341559443154668&programming_language=python#natural-language-classifier).
- Provision an instance of Watson Studio [instance](https://cloud.ibm.com/catalog/services/watson-studio)
- Log into Watson Studio & provision a Watson Natural Language Classifier instance within Watson Studio
    - getting started
    - create a project
    - Choose standard project
    - Choose assets
    - Scroll down to models and create new natural language classifier model
    - Name your classifier 
    - Choose to either upload a CSV for classification or create an empty class to add data to later
        - Creation of a training set of data by uploading raw CSV data and doing data cleansing in data refinery to build                   sample set of data for training(better accuracy through shorter test, file should contain sample classifiers and sample questions/statements to be classified)
     
     
     
     
## Hints and Tips:
- Natural Language Classifier will return the best matching classes for a sentence, phrase, or paragraph
- Training an ML classifier requires a “representational set” of training data. If we can provide an accurate sample of data that looks like the broader set, we can train on that smaller sample, giving us much quicker results.
- You can improve the performance of this classifier in two ways. The first is by defining additional target classes and providing new training data for those classes.Do not fabricate new training data, take training data directly from user input from logs or other sources. This helps ensure representativeness — no matter how clever you are any training data you fabricate is not going to match the way users interact with your system






