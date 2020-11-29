# p13n-search-and-learn-2-rank

This repository demonstrates the architecture of a personalized search system on an ecommerce site, which facilitates delivering personalized user experience in an efficient and scalable way. It contains three parts - 

### 1. A Search Engine 

We use AWS Elastic Search as our search engine. It uses bm25 to do keyword matching and ranks results accordingly. 

* This [notebook](https://github.com/catwhiskers/p13n-search-and-learn-2-rank/blob/main/01-data-preparation.ipynb) demonstrates how to index product information into elastic search engine. 

### 2. A Search Relevance Optimization Mechanism 

Keyword matching oriented methods could be vulnerable while some content providers perform search engine spamming, i.e. putting irrelevant information in the content in order to getting more exposure than it deserves for its keywords, leading to unsatisfactory search experience. Therefore we need to calculate accurate relevance scores based on semantics and user intentions between contents and search queries. It is known as [learning to rank](https://en.wikipedia.org/wiki/Learning_to_rank) problem.  

* This [notebook](https://github.com/catwhiskers/p13n-search-and-learn-2-rank/blob/main/04-search_optimiztion-bert_plus_gbdt.ipynb) demonstrates how to use bert to extract the embedding which represents semantic information of contents and search queries and use the embedding as input features to train a ranking model. 

* This [notebook](https://github.com/catwhiskers/p13n-search-and-learn-2-rank/blob/main/04-search_optimiztion-tfidf.ipynb) uses tf-idf as a baseline of our ranking model. 


### 3. A Personalized Ranking Mechanism 

To optimize user engagement metrics further, personalized ranking is an effective strategy. In this stage, we will users' clickstream data to compile their preferences and calculate the relevance scores between contents and users, and rank the results accordingly. 

* This [notebook](https://github.com/catwhiskers/p13n-search-and-learn-2-rank/blob/main/02-personalize_ranking_movielens.ipynb) demonstrates how to use AWS Personalize to build a personalized ranking mechanism 

* This [notebook](https://github.com/catwhiskers/p13n-search-and-learn-2-rank/blob/main/03-movielens_tfrs_ranking.ipynb) demonstrates how to use a self-defined algorithm on SageMaker



