# Topic Modelling with Latent Dirichlet Allocation (LDA) on Journalistic Turkish Texts

## Introduction

This research consists of scraping websites, pre-processing of the data and model training. The first step is scraping the RSS feeds of Hürriyet and Cumhuriyet newspapers, but the format can not be processed directly by the algorithm. Thus, I need pre-processing steps to make the raw text data clean and useful. Pre-processing includes parsing the text data, tokenization, stopwords and removing. After the pre-processing step, a dictionary and a corpus is created. Then I apply the data to fit the LDA topic model. Finally, the fitted model will be used for clustering.

## DataSet

This dataset consists of articles I scraped from RSS feeds of Hürriyet and Cumhuriyet newspapers' latest news category.

## Pre-Processing 

- Text is converted to lowercase. Thus, words with uppercase are not considered different words from their lowercase equivalents.
- Replace special characters with their corresponding Turkish characters.
- Remove non-Turkish-letter characters such as digits or punctuation marks.
- Split text into a list of words.
- Remove Turkish stopwords (optional).
- Return as a list or as one string (depends the parameter).

Note that pre-processing usually have lemmatization and stemming steps, too. But I skipped those steps for two reasons. The first reason is Turkish language being hard to process because of the complex morphology and the way morphology interacts with syntax. The second reason is there are no well-defined open source Turkish NLP libraries I can benefit from at the moment.

## LDA

I used gensim.models.LdaModel to build the LDA model with 20 topics. To evaluate this model I calculated the Perplexity and Coherence Score. 
- A low perplexity means the probability distribution is good at predicting the sample. 
- High topic coherence scores shows a good topic model generating coherent topics that can be described by a short label. 

The Perplexity of the LDA model is -9.005 and the Coherence Score is 0.472.

## pyLDAvis

In order to show the topic model, I used pyLDAvis package for interactive topic model visualization and get the html file pyLDAvis_25.html as shown. 

- Each circle on Intertopic Distance Map shows a topic. These circles are proportional to topic frequencies, so if a circle is more large, that topic is more prevalent.

- If you have a big, non-overlapping circles scattered around the chart, that means you have a fairly good topic model.

- If you end up with too many topics, you will have many overlaps with small sized bubbles being clustered in one region of the map.

- If you select a circle or a topic, you will see it highlighted and when you look at the right-side, it will automatically give you the most relevant terms for that topic. Red bars indicate term-frequency within the selected topic. Gray bars indicate overall term-frequencies across the corpus.

![pyLDavis](https://user-images.githubusercontent.com/43665538/58829755-4b946480-8651-11e9-8fa7-86b8d4842657.png)
