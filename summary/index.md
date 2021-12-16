---
layout: page
title: Summary
date: 08-12-2021
comments: false
---
## Before talking about what didn't work, let's talk about what we've achieved.
We have shown that it is possible to successfully merge huge datasets (quotebank and wikiData) and use them together even with their oftentimes incomplete and missing datas.
Multiple interesting exploratory data analysis techniques ranging from length analysis, distribution analysis via heatmaps and histograms, and even semantical analysis with 
toolboxes like bertTopic and vaderSentiment have allowed us to have a good overview of the dataset.
From this the strenghs and weaknesses of our dataset have been identified : it's huge, ranges over a very varied set of topics (politics, sports, science...) but it also contains many biases like being too tied to american/english press, contains a huge number of quotes extracted solely from Trump,  religious topics are mainly from American religions...

With all this in mind, we now came back to our original idea of trying to predict quote popularity from the gathered material.
We have yet again successfully shown it is possible to train multiple  machine learning models on a huge chunk of the dataset using only a modern laptop as hardware. A big diversity of models has been tried trying to make relations appear between popularity of a quote and data. Linear regression, decision trees, Logistic regression as well as linear support vector machines are all very well developped and understood tools for the data scientist and they have been tried out on our dataset.

## And that's when we talk about what did not work
Analysis of the results of these different models show that overall, they do "sense" that some features are relevant and there is indeed at least partial predictability of quote popularity.
But the fact that they do not work is actually good, and quite reassuring! The real world is an extremely complicated object and if quote popularity were reliably predictable with the mathematical tools used we would be quite rich right now! It totally makes sense, and the statement we have to extract from our models is the following : 
"Only fools would try to predict everything from a bunch of data that is very disconnected from the real world and obviously very incomplete". Here the data is incomplete because we do not
tell our model what trend is going on in the real world, who is the current president, who is the current newspaper writer at the NY Times and what he enjoys and a bunch of features that can randomly be a part of what makes one specific quote popular... A good warning and reminder for all fellow data scientists out there that not everything can be solved by creating a big dataset and fitting a model, it can sometimes be only a part of the solution, or not a solution at all.





