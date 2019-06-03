# Thesis---TopicModelling
Topic Modelling with LDA using Journalistic Turkish Text

This research consists of scraping websites, pre-processing of the data and model training. The first step is scraping the RSS feeds of Hürriyet and Cumhuriyet newspapers, but the format can not be processed directly by the algorithm. Thus, I need pre-processing steps to make the raw text data clean and useful. Pre-processing includes parsing the text data, tokenization, stopwords and removing. After the pre-processing step, a dictionary and a corpus is created. Then I apply the data to fit the LDA topic model. Finally, the fitted model will be used for clustering.
