# Watson Natural Language Classifier, Watson Studio & Data Refinery

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

## Process to train/test a classifier in Watson Natural Language Classifier Pt. 1: 

Prerequisites
- IBM Cloud account: If you do not have an IBM Cloud account, you can create an account [here](https://cloud.ibm.com/)
- Basic knowledge of Watson Natural Language Classifier by viewing [docs](https://cloud.ibm.com/docs/services/natural-language-classifier?topic=natural-language-classifier-natural-language-classifier&cm_mc_uid=08582511162115581306652&cm_mc_sid_50200000=48334731559443154666&cm_mc_sid_52640000=20154341559443154668&programming_language=python#natural-language-classifier).
- Provisioning of the following services: Watson Studio, Watson Natural Language Classifier, Data Refinery


- Provision an instance of Watson Studio [instance](https://cloud.ibm.com/catalog/services/watson-studio)
![test](https://github.com/bmguillo/NLC_WatsonStudio_DataRefinery/blob/master/img/WatsonStudioProvisioning1.png)
![test](https://github.com/bmguillo/NLC_WatsonStudio_DataRefinery/blob/master/img/WatsonStudioProvisioning2.png)

- Log into Watson Studio & provision a Watson Natural Language Classifier instance within Watson Studio
    - getting started
    - create a project
    - Choose standard project, name it
    - Choose assets within the project
![test](https://github.com/bmguillo/NLC_WatsonStudio_DataRefinery/blob/master/img/WatsonStudioGettingStarted.png)
![test](https://github.com/bmguillo/NLC_WatsonStudio_DataRefinery/blob/master/img/WatsonStudioWelcome.png)
![test](https://github.com/bmguillo/NLC_WatsonStudio_DataRefinery/blob/master/img/WatsonStudioNewProject.png)
![test](https://github.com/bmguillo/NLC_WatsonStudio_DataRefinery/blob/master/img/WatsonStudioCreateAStandardProject.png)
 

 ## Use Data Refinery to Perform Data Cleansing to build training & test data sample sets
- Within the assets section of Watson Studio project, choose CSV file and click refine under actions
- Upload raw CSV data and doing [data cleansing](https://dataplatform.cloud.ibm.com/docs/content/wsj/refinery/refining_data.html#refine) via refine option in data refinery
    - Remove irrelevant data not needed to train
    - Cleanup invalid data
    - Remove excess data (only need sample)
    - Merge columns
    - Remove blanks(missing data)
    - Remove column headers so that Watson NLC can properly classify the data e.g. [weather sample](https://github.com/bmguillo/watsonnaturallanguageclassifier_hrjobrecommendations/blob/master/weather_data_train.csv)  
![test](https://github.com/bmguillo/NLC_WatsonStudio_DataRefinery/blob/master/img/WatsonStudioCSVAssetUpload.png)
![test](https://github.com/bmguillo/NLC_WatsonStudio_DataRefinery/blob/master/img/WatsonStudioCSVAssetUpload2.pngl)

- Run through data refinery flow to process the changes and create new file with shaped extension
![test](https://github.com/bmguillo/NLC_WatsonStudio_DataRefinery/blob/master/img/WatsonStudioAssetRefine.png)
![test](https://github.com/bmguillo/NLC_WatsonStudio_DataRefinery/blob/master/img/WatsonStudioDataRefineryFlow.png)
![test](https://github.com/bmguillo/NLC_WatsonStudio_DataRefinery/blob/master/img/WatsonStudioDataRefineryFlow2.png)
![test](https://github.com/bmguillo/NLC_WatsonStudio_DataRefinery/blob/master/img/WatsonStudioDataRefineryFlow3.png)

- Create sample training set from data refinery flow output file with shaped extension
![test](https://github.com/bmguillo/NLC_WatsonStudio_DataRefinery/blob/master/img/WatsonStudioDataRefinerySample.png)  
![test](https://github.com/bmguillo/NLC_WatsonStudio_DataRefinery/blob/master/img/WatsonStudioDataRefinerySample2.png)
![test](https://github.com/bmguillo/NLC_WatsonStudio_DataRefinery/blob/master/img/WatsonStudioDataRefinerySample3.png)


## Process to train/test a classifier in Watson Natural Language Classifier Pt. 2(sample classifiers in training data & funnel real data to test creation of new classifiers)

- Provision a Watson Natural Language Classifier instance within Watson Studio
- Scroll down to models and create new natural language classifier model
- Name your classifier 
- Choose to either upload a CSV for classification or create an empty class to add data to later
- For this example, we will upload a CSV via the upload to project button


## Hints and Tips:
- Natural Language Classifier will return the best matching classes for a sentence, phrase, or paragraph
- Training an ML classifier requires a “representational set” of training data. If we can provide an accurate sample of data that looks like the broader set, we can train on that smaller sample, giving us much quicker results.
- You can improve the performance of this classifier in two ways. The first is by defining additional target classes and providing new training data for those classes.Do not fabricate new training data, take training data directly from user input from logs or other sources. This helps ensure representativeness — no matter how clever you are any training data you fabricate is not going to match the way users interact with your system
- Better accuracy through shorter test file
- Final training set file should contain sample classifiers and sample questions/statements to be classified     
     

## Links
- [NLC Best Practices:](https://medium.com/ibm-watson/watson-natural-language-classifier-fb66206be6de)
- [Classification of Unstructured Text in NLC](https://medium.com/ibm-watson/cognitive-classification-of-text-and-what-it-can-do-for-you-514378af1e08)
- [NLC & NLU](https://medium.com/@AlexAlBasosi/cognitive-workshop-series-natural-language-classifier-and-natural-language-understanding-898db567f188)
- [Realtime Feedback Analysis with NLC](https://medium.com/@shyampurk/realtime-customer-feedback-analysis-with-ibm-watson-natural-language-classifier-cc411593ae4d)
- [NLC & Watson Studio](https://medium.com/@shyampurk/realtime-customer-feedback-analysis-with-ibm-watson-natural-language-classifier-cc411593ae4d)
- [Classify Job Descriptions in NLC](https://medium.com/ibm-watson/classify-job-descriptions-with-watson-natural-language-classifier-fca735ff2f3c)
- [Training a Classifier Video](https://developer.ibm.com/videos/create-and-train-a-classifier-for-watsons-natural-language-classifier-service/)
- [Developer blog on text classification](https://developer.ibm.com/blogs/getting-started-with-text-classification/)





