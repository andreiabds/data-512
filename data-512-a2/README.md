# A2: Bias in data - Analyzing Bias in the Wikipedia Talk corpus Toxicity dataset

Here is the [License](https://github.com/andreiabds/data-512/blob/main/data-512-a2/LICENSE) to use the information on this repository.

## Introduction
The objective of this analysis is to identify what, if any, sources of bias may exist in the Wikipedia Talk corpus Toxicity dataset, and to develop testable hypotheses about how these biases might impact the behavior of machine learning models trained on the data, when those models are used for research purposes or to power data-driven applications. 


## Data Source
The data used on this repository is called the [Wikipedia Talk corpus](https://figshare.com/projects/Wikipedia_Talk/16731), and it consists of three datasets. Each dataset contains thousands of online discussion posts made by Wikipedia editors who were discussing how to write and edit Wikipedia articles. Crowdworkers labelled these posts for three kinds of hostile speech: “toxicity”, “aggression”, and “personal attacks”. Many posts in each dataset were labelled by multiple crowdworkers for each type of hostile speech, to improve accuracy.

This repository focused on the Toxicity dataset ([Wikipedia Talk Labels: Toxicity](https://figshare.com/articles/dataset/Wikipedia_Talk_Labels_Toxicity/4563973) ), that is separated in 3 different datasets:
- toxicity_annotations.tsv
- toxicity_annotated_comments.tsv
- toxicity_worker_demographics.tsv 

More information about the Wikipedia Talk corpus (and the Toxicity dataset especifically) is available [here](https://meta.wikimedia.org/wiki/Research:Detox/Data_Release#Toxicity).

## Final Data 

|Column Name |Data Type	|Description|
|------------|-----------|------------|
|rev_id	|float	|Comment identifier	|
|worker_id	|int	|Annotator identifier	|
|toxicity	|int	|Boolean to indicate whether the score was toxic.	|
|toxicity_score	|float	|Score given by annotator that varies from -2 (very toxic) to 2 (very healthy).	|
|worker_id_r	|float	|Annotator identifier	|
|gender	|string	|Gender of annotator	|
|english_first_language	|float	|Boolean to indicate whether the annotator is an English native speaker.	|
|age_group	|string	|Age group of annotator.	|
|education	|string 	|Education level of annotator.	|
|toxicity_score_disagreemen	|float	|Standard deviation of toxicity score within a question.	|


## The Analysis
In our analysis we explored two hypothesis.

### 1. Is there a bias based on native English vs non-native English? 
Do native English speakers annotators label comments more harshly (more toxic) than non-native spearkers?

Because the comments are written in English, having domain of the English language and its culture would probably help an annotator detect toxicity more effectively. 

The dataset clearly had a bias toward non-native speakers. The majority of annotators did not have English as their first language. 

![alt text](https://github.com/andreiabds/data-512/blob/main/data-512-a2/language_distribution.jpg?raw=true)

Comparing the distribution of percentage toxicity (percentage of comments that they annotated as toxic), we notice that native speakers have a distribution leaning further to toxic labels than non-native speakers.
(We can see the graphs for native and non-native speakers, respectively). 

![alt text="Native Speaker"](https://github.com/andreiabds/data-512/blob/main/data-512-a2/hist_percentage_toxicity_native.jpg?raw=true) ![alt text="Non-Native Speaker"](https://github.com/andreiabds/data-512/blob/main/data-512-a2/hist_percentage_toxicity_nonnative.jpg?raw=true)

After doing a Statistical test, we concluded that <b>native speakers are harsher (i.e., give more toxic scores) than non-native speakers when annotating comments</b>.


### 2. Is there a bias based on gender? 
Does the annotator's gender affect the toxicity score? 

The dataset is not balanced between the different gender categories. Male is the most represented gender, followed by female. 

![alt text](https://github.com/andreiabds/data-512/blob/main/data-512-a2/gender_distribution.jpg?raw=true)

We compared male and female percentage toxicity, and we noticed differences in its distribution, with females seeming to give more toxic labels. Below,we display the distributions of percentage toxicity for male and female population respectively.  


![alt text](https://github.com/andreiabds/data-512/blob/main/data-512-a2/hist_percentage_toxicity_male.jpg?raw=true) ![alt text](https://github.com/andreiabds/data-512/blob/main/data-512-a2/hist_percentage_toxicity_female.jpg?raw=true)

After doing a Statistical test, <b>we concluded that females give toxic labels more often than males</b>.


## Final Thoughts

In this analysis we showed that there are language and gender biases in the dataset. 

These biases will have an effect on possible data solutions derived from this dataset. It is important to be aware and take action to mitigate those biases. 

We discuss a few implications of these findings at the end of our analysis in this [Jupyter notebook](https://github.com/andreiabds/data-512/blob/main/data-512-a2/%5BA2%20Analysis%5D%20Finding%20Bias%20in%20Data%20.ipynb).









