---
layout: page
title: Data
date: 08-12-2021
comments: false
---


The goal of this project is to predict which factor that characterize a quote contributes for make it viral. For this purpose we use the Quotebank dataset complemented with the informations collected from Wikidata. Quotebank consist of a dataset of 178 million unique quotations, extracted from 196 million Engish news papers pubished between Agoust 2008 and April 2020. Wikidata is a databese containing information about a subjects being in Wikimedia. Therefore we will use it to gather the charactheristics about the speaker of each of the quotes.

<img src="../assets/img/plots_data/raw_data.svg">

## What makes a quote to be viral

<img src="../assets/img/plots_data/occ_hist.svg">

Before diving into the question we will start by exploring the data extracted from both dataset. The first thig that we will do is to define what is a viral quote. For doing so we have analyzed the number of occurences of all the quotes present in Quotebank. We see that the majority of the quotes occours one time and that the 99% of them occures less than 100 times. For this reason we decided to set the threshold for defining a vira quote at 100 occurences. Therefore we obtained that in our dataset only the 0.5% of quotes are viral.

## What can we learn from the data

After difining the notion of virality, we are interested into finding the relevant features that may have an impact on the virality of the quote. Initially. we explored the distribution of the speaker’s features weighted by the nuber of occurences for each quote.

<div align="center"> {%include plotly_graphs/age_hist.html%}</div>

By observing the datage distributions we can see that more than half of the speakre in our dataset have an age that ranges between 19 and 66. This is expected since the speakers benefitting from media coverage are mainly young adults and middle-aged men.

<div align="center"> {%include plotly_graphs/gender_hist.html%}</div>

By inspecting the gender for the speakers of all the quotes we observe that the majority of speakers are male or female, and that only a small minority of the quotes are represented by other genders. From the distribution of the occurence of quotes based on genders we can see that males are quoted more often by the media and their quotes are repeated more times than females.

<div align="center"> {%include plotly_graphs/occupation_hist.html%}</div>

The third feature that we investigate for characterizing the spekear of a quote is its occupation. From the result of all quotes we can see that the three main profession are politicians, sport related professions and artistic profession( (actors, writers, singers, journalists etc…) business-related professions (businesspeople, lawyers, …). Since the dataset is made from newspapers articles, it makes a lot of sense that politicians would be the most quoted. Sport plays a very important role in our sociaty, and almost aevery newspaper has a sport section, thus it make sense that it represent a main profession in the quote dataset. For similar reason to sport, it is expected that also artistic and business-related profession would rank high in list of professions with most media coverage. Moreover, it should be noted that often politicians are not only assigned a single occupation, with many also being or having been lawyers, businesspeople, actors. This is clearly visible from the co-occurency matrix of the occupations. It is interesting to note that researcher rank as the second most cited occupation when considering only the number of different people contained in the dataset, but don’t even rank in the first 15 when weighting by the number of quotes and number of occurrences. This suggests that several researchers may be interviewed and quoted on a particular subject, but each of their opinions would not be repeated very often, nor there would be a significant number of researchers which are asked for their opinion particularly often compared to the other professions.

<div align="center"> {%include plotly_graphs/nationality_hist.html%}</div>

The last feature that we consider for the speakers is their nationality. As we can see from these results, there is a big over-representation of people from english-speaking countries in the Quotebank dataset. This is not very surprising, as the dataset is built from newspaper articles written in English. We dicided to discard other features like ethnicity and religion, since for more than 90% of speakers in the whole dataset these information was not present.

For this study we are also interested on how the combination of different features for speakers may influence the virality of a quote. Therefore, in further analysis we looked at the co-occurences between values of different features. By combining gender and occupation we can observe that for some occupations the ratio between males and females is not the same as for most other occupations. This is clearly visible for occupations like politician, football players, businesspeople and film directors. These differencese are important to take into account when evaluation the coefficients assigne by the model to the gender, when one of the unbalanced professions is deemed important to describe the virality. By observing the co-occurence between gender and nationality, we once again note that for every nation the number of women is lower than that of men.However, the ratio between the number of mails and females does not appear to change significantly across nations, which is good when we will use these features for constructing a model, since it avoids hidden bias of the models. 
Finally, by looking at the occupation in combination with nationality we can see that politicians are the most quoted aross all countries. Howevere, we can clearly notice that there are some professions which are very uncommon in certain nations while being very common in others. A clear exemple of this is the american football player occupation, which is completely missing from countries such as India and Russia. As in previous cases, when we will need to pay attention to the coefficient assigned by the models to the nationality when one of the unbalanced professions is deemed important to describe the virality.

After studying how the features of speakers may infuence the virality of the quote, we now concentrate on the actual characteristics for each single quotes. As first thing, We analyzed the distributions of lenghts of all quotes in Quotebank. From these results we can observe that 50% of the quotes have a length smaller than 20 words and that 95% of the quotes are less than 60 words.
