---
layout: page
title: Data
date: 08-12-2021
comments: false
---
When working on a data science project, it is always important to thorougly visualize, explore and understand what is going on in the data. 


## Extract data from the datasets
This little diagram illustrates how we have used the two Datasets described in the [Introduction](/introduction/) to extract the informations which we expected to be useful for our task.

<img src="../assets/img/plots_data/raw_data.svg">


## What is a viral quote?
We have, up until this point, used the adjective 'viral' for a quote, without ever defining it or explain why such a distinction can be made between quotes.

To do so, let's look at how the number or occurrences (which is the number of times a particular quote was found in different newspaper articles) is distributed across all quotes in the Quotebank dataset:

<img src="../assets/img/plots_data/occ_hist.svg">

| Percentile | Min | 25.0% | 50.0% | 75.0% | 95.0% | 97.0% | 99.0% | 99.5% | 99.9% | Max    |
|------------|-----|-------|-------|-------|-------|-------|-------|-------|-------|--------|
| **Value**  | 1   | 1     | 1     | 2     | 10    | 17    | 55    | 90    | 215   | 282552 |

As you may already have noticed, more than half (63.3% to be precise) of quotes only appear in newspapers a single time!


#### defining precisely the mathematical ground for the question
We have been throwing around the adjective "viral" for quotes. Because we are at our essence mathematicians, let's give it a strict mathematical definition : a quote is viral if it has occured more than a 100 times. This value of 100 is not chosen at random, indeed only 0.5% of all quotes occur more than 100 times which we think is a nice metric to define popularity.


## Finally show us results!!!

Now that we have taken care of merging the datasets and defining the maths, let's take a look at what our dataset is telling us!

<div align="center"> {%include plotly_graphs/age_hist.html%}</div>

Half our speakers are between 19 and 66 years old. Again we see why it's important to take a look about the data and think : some speakers are literally two thousand years old, because some of the quotes come from long dead people! It then falls to us to decide if we want to keep them for training or not, if it makes sense to consider long dead people in our popularity features. 

<div align="center"> {%include plotly_graphs/gender_hist.html%}</div>

From this we see another immediate bias that our models could be victims of : As always, middle aged males are an over represented class of people, we have to be careful and maybe discard them from the features because what our models would probably learn from this is that to be successfully quoted you have to be aged and a male! That's not a conclusion that makes sense...

<div align="center"> {%include plotly_graphs/occupation_hist.html%}</div>

Politicians, sports coaches and players, artists, researchers, writers, singers... We observe the usual distribution of jobs in newspapers quotes. 
Some interesting things that might not be so obvious : Politicians oftentimes have a second occupation associated (lawyers, actors, business people). Also, while there are many quotes about research papers they come from different people, basically, researchers appear once each when their research is out and then don't appear again. These kind of things are good to note because it could help us debug and explain certain things about how our model takes decisions.

<div align="center"> {%include plotly_graphs/nationality_hist.html%}</div>

The last feature that we consider for the speakers is their nationality. As we can see from these results, there is a big over-representation of people from english-speaking countries in the Quotebank dataset. This is not very surprising, as the dataset is built from newspaper articles written in English. We dicided to discard other features like ethnicity and religion, since for more than 90% of speakers in the whole dataset these information was not present. Again we have to be careful and remind ourselves that our model will be trained specifically on english speaking countries and might not work as well if applied elsewhere!

As a last sanity check, instead of studying data piece by piece, we tried pairing them in what is called co-occurences matrixes. This allows us to be on the lookout for weird relations between data and think 2D instead of simply 1D : 
The male/female distribution over nations remains the same. We also notice that occupations are not quoted in the same proportions everywhere. American football players are more quoted in the American press, whilsts soccer players are more quoted in the UK press. In Russia and India there are close to no quotes on either. There are similar differences in occupations like actors, researchers etc... Another cool example is germany, where they seem much more inclined to quote researchers and research papers. 
Again, this reinforces the fact that our model will learn to think about popularity from an American based point of view, and might miss out on crucial factors if applied to other countries newspapers later on.


So even though we have used very basic tools, we can see how much information we extracted from the dataset and how much better we can understand if our model takes weird decisions and makes errors. Being a data scientist isn't only about being cool and using neural nets, it's also important to understand the base on which you build everything else!
