+++
author = "David Salter"
title = "What is Machine Learning ?"
date = "2024-04-07"
description = "A gentle introduction to machine learning  discussing supervised learning, unsupervised learning and reinforced learning."
tags = [
    "ml",
]
+++
Machine Learning (ML) is a subset of Artificial Intelligence that is concerned with predicting results from given datasets.

![What is Machine Learning ?](/static/assets/jason-leung-HBGYvOKXu8A-unsplash.jpg)

## Machine Learning vs Traditional Calculations

Machine Learning is particularly useful where we need to predict results from a given dataset. For example, consider that we need to predict the quality of wine. Using traditional calculations, we would need to measure different factors such as acidity, pH, alcohol quantity etc. and try to work out a mathematical formula that calculates quality based upon the different variables we have. You can imagine running multiple laborious experiments and drawing graphs to work out how each factor defines the quality.

With machine learning, we define a model by supplying a dataset of samples and allow the Machine Learning algorithm to work out all of the relationships between the different factors for us. The machine model "learns" the relationships between the data and how they affect the quality of the wine.

There are 3 basic types of Machine Learning that offer slightly different approaches to this type of problem.

## Supervised Learning

With supervised learning, we provide a dataset to a Machine Learning model so that it can work out the relationships within the model. The dataset that we supply contains not only the data (acidity, pH, alcohol quantity etc. from our example above), but also the result (quality of wine) for each row in the dataset. This is known as training where the dataset is typically called the _training_ dataset.

After the model has been trained, we supply the model with a second dataset so that we can perform validation on the model and see how well it performs. This involves using a _test_ dataset which must be different from the training dataset. If we're happy that the model gives accurate results with the test dataset, then we can use the model to start predicting results. If we're not happy that the testing was successful, we can go back and make changes to the model and go through the train/test/evaluate cycle again until we're happy that the model is generating good predictions.

Supervised learning is an excellent tool for problems such as our predictions of wine quality. A supervised model could predict the quality of the wine on a scale of 1 to 10. This is called a _regression model_ where a numeric value is obtained from the model.

Alternatively, we could use a _classification model_ to work out the classifiers for data within a dataset. For example, examining cancerous cells, we could use supervised learning to predict whether cells are cancerous or benign. In this situation, we're not giving a number to the prediction, we're predicting the likelihood of cells being in one of two states (cancerous or benign) or _classifications_.

## Unsupervised Learning

With unsupervised learning, we don't provides the answers with the dataset for the model. Again, using the wine example above, with unsupervised learning we wouldn't provide the quality factor within the dataset. Supervised learning is more about finding clusters within data that can then be investigated and named outside of the model. An example of unsupervised learning could be checking email to see if it is spam or not. The dataset supplied in this case would not have a factor saying that an email was spam or not. Instead, the model could classify the data into one of two clusters that could then be marked as either spam or non-spam.

## Reinforcement Learning

Finally we have reinforced learning. In this situation, the model is given rewards if certain actions occur. In a similar fashion to unsupervised learning, machine learning does not have the labelled result (our wine quality) within the dataset.

## Summary

In this post, we've introduced what Machine Learning is and identified the 3 main types: _Supervised Learning_, _Unsupervised Learning_ and _Reinforcement Learning_.

I hope you've found this useful and it's caused you to have an interest in Machine Learning.

Happy Learning !

## Credits

Photo by <a href="https://unsplash.com/fr/@ninjason?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Jason Leung</a> on <a href="https://unsplash.com/photos/HBGYvOKXu8A?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText">Unsplash</a>

