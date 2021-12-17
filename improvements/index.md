---
layout: page
title: Improvements
date: 08-12-2021
comments: false
---

Going further in our research, we could have done the following:

- Extracted more features from the data avilable to us:
it is reasonable to think that, if we added other features accounting for links with real-world event (for example presidential elections in the USA, movies release, festivals and events etc.) which have an impact media coverage and hence on our quotes, we may have enabled our models to perform better.


- Augmenting features:
exploring the joint contribution of the features we have extracted (such as considering the impact of being an (American, Male, Politician) has on the quotability may also have been insightful.


- Selecting features:
An abundance of some features were extracted by us and used to train our models. This was possible thanks to the large number of training samples available. For the models which worked, L1 regularization could be used and tuned to allow choosing a model using only a subset of these features but achieving very close performance to the un-regularized model

- Trying more advanced models:
With more time and computational power, it  makes a lot of sense to train a neural network. They are well adapted to situations like ours with lots of data and complicated relationships between features/prediction. If this path is chosen, extra vigilance should be put on the biases that can be introduced from the dataset. We would not want the model to become racist or sexist for example.
