# NLP Project

## Introduction

This project is a sentiment classifier on the IMDB sentiment dataset using several approaches.

## Dependencies
To install the dependencies used in this project:
```
pip install -r requirements.txt
```

## Architecture of project
In this folder, you will find 2 notebooks for naives bayes method  (with and without pretreatements), 2 notebboks for logistic regression method (with and without pretreatements), 1 file for fasttext method.and the requirements.txt for dependencies.

## The dataset

The IMDB sentiment dataset is a collection of 50K movie reviews, annotated as positive or negative, and split in two sets of equal size: a training and a test set. Both set have an equal number of positive and negative review. The dataset that we have used is from [HuggingFace](https://huggingface.co/docs/datasets/).


## Naive Bayes classifier
The `naive_bayers.ipynb` notebook implements a simple sentiment analysis classifier using naive bayes model. 

The `naive_bayers-pretreatement.ipynb` notebook implements a simple sentiment analysis classifier using naive bayes model but with pretreatment methods such as stemming, lemmatization.

## Logistic regression

The `logistic_regression.ipynb` notebook implements a simple sentiment analysis classifier using logistic regression.

The `logistic_regression-pretreatement.ipynb` notebook implements a simple sentiment analysis classifier using logistic regression but with pretreatment methods such as stemming, lemmatization, removing html tags.

For the two notebooks, we have first train our model using words frequencies using CountVectorizer (BoW) and then using hand-made features. 
We have implemented 4 features: 
* 1 if "no" appear in the doc, 0 otherwise
* 1 if "!" is in the document, 0 otherwise
* Number of words in the document which are in the positive lexicon
* Number of words in the document which are in the negative lexicon

To generate positive and negative lexicons, we have use the resources provided by [VADER sentiment](https://github.com/cjhutto/vaderSentiment).

## FastText

The `fast_text.ipynb` notebook implements a simple sentiment analysis classifier using fastText with pretreatement and hyperparameters tunning. In this notebook, our code will generate two files `train_file.txt` and `test_file.txt` with the following format for each line:
```
__label__<your_label> <corresponding text>
```
Those files are used to train the fastText model. 