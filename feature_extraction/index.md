---
layout: page
title: Feature Extraction
date: 08-12-2021
comments: false
---

Exploratory data analysis can be done by hand parsing through data and generating statistical graphs (length of tweets, who said it, the date, the amount of citations…). 

Because of recent advances in computational techniques, a whole new field called NLP (Natural Language Processing) allows us to completely shift the analysis paradigm. This allows us to directly address the semantics of the tweets instead of trying to extract relevant information from mathematical features.
To achieve this on our dataset, we used two libraries : bertTopic and vaderSentiment.


##What we wanted from BertTopic and what we expected  :
To explain briefly without going into mathematical details, BertTopic allows us to group tweets into dense clusters defined around subjects. There are also very interesting visualisation tools packaged with the modelling technique. In our case, we expected the tool to give us clusters based on popular subjects in english newspapers (Trump, american football…), which would allow us to define more clearly what is popular and what isn’t in this kind of press.

##The results of bertTopic : 
=> show the topic split and comment on the fact that it just shows the basic distribution of newspaper stories ( politics then sports with specifically american football then research breakthroughs etc)


##What we wanted from vaderSentiment and what we expected  :
Similarly to bertTopic, vaderSentiment’s main idea is to classify our quotes into sentiment based groups. The idea behind this is to see if we can find relevant information on how super popular quotes are structured. Are they mainly pessimistic or is it better for the quoter’s tone to be positive and optimistic, or it doesn’t actually matter, is one of the questions that we expect to be addressed by vaderSentiment.

##The results of vaderSentiment : 
Plots + comments 
    

