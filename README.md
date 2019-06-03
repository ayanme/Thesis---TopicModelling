# Topic Modelling with Latent Dirichlet Allocation (LDA) on Journalistic Turkish Texts

## Introduction

This research consists of scraping websites, pre-processing of the data and model training. The first step is scraping the RSS feeds of Hürriyet and Cumhuriyet newspapers, but the format can not be processed directly by the algorithm. Thus, I need pre-processing steps to make the raw text data clean and useful. Pre-processing includes parsing the text data, tokenization, stopwords and removing. After the pre-processing step, a dictionary and a corpus is created. Then I apply the data to fit the LDA topic model. Finally, the fitted model will be used for clustering.

## DataSet

This dataset consists of articles I scraped from RSS feeds of Hürriyet and Cumhuriyet newspapers' latest news category.

## Pre-Processing 

1. Text is converted to lowercase. Thus, words with uppercase are not considered different words from their lowercase equivalents.
2. Replace special characters with their corresponding Turkish characters.
3. Remove non-Turkish-letter characters such as digits or punctuation marks.
4. Split text into a list of words.
5. Remove Turkish stopwords (optional).
6. Return as a list or as one string (depends the parameter).

## LDA

I used gensim.models.LdaModel to build the LDA model with 20 topics. To evaluate this model I calculated the Perplexity and Coherence Score. A low perplexity means the probability distribution is good at predicting the sample. High topic coherence scores shows a good topic model generating coherent topics that can be described by a short label. The Perplexity of the LDA model is -9.005 and the Coherence Score is 0.472.

In order to show the topic model, I used pyLDAvis package for interactive topic model visualization and get the html file pyLDAvis_25.html as shown. The left side display the intertopic distance map and the right side display the top-30 most salient terms for the topic.

![pyLDavis](https://user-images.githubusercontent.com/43665538/58829755-4b946480-8651-11e9-8fa7-86b8d4842657.png)
