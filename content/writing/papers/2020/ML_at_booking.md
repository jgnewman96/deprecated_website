---
title: "150 Succesfful Machine Learning Models: 6 Lessons Learned at Booking.com"
date: 2020-05-18T16:21:18-05:00
draft: true
tags: ['Machine Learning', 'Software Engineering']
categories: ['Papers']
---

[By Lucas Bernardi, Tehmis Mavridis, Pablo Estevez](https://dl.acm.org/doi/10.1145/3292500.3330744)

## Summary

Focus is not an algorithmic advances but rather how it has derived value to the company. In depth look at the 150 models they have in production

specific to booking
    - bad reccomendation is much worse: a bad travel is worse than a bad song
    - very low number of actual results, guests travel quite infrequently, past history is not always relevent

difficult to quantify the impact that models are having on the business

Lesson for each of the stages, Inception, Modeling, Deployment, Monitoring and Evaluation, and conclusions.

*Inception*
- a tool to help you learn from your users.
- some very specific, optimize the size in a layout
- some very broad and are actually inputs into other things. model for how flexible a user is in the dates of their trip

model categories:
- traveler preference models: how flexible are they about aspects of their travel, dates location etcc
- traveller context models; what is the theme of the trip, who are they going with, why are they going, what is the purpose of the trip
- item space navigation models; take in data about user interactions, clicks scrolling etc and then try to show most relevent items
- user interface optimization models: what the user interface should look like
- content curation: what format should content come in: free text, images
- content augmentation: augment that content with context, example how good of a value is this, what is the price trend on this

all of the different models have provided value

*Modeling*
- they estimate value using RCTs. Look at conversion, customer service tickers or concellations.

offline performance is defined as tradional mean squared error on test / train

not necessarily a correlation between offline performance and business value gain

how can this be explained
- value performance saturation: gains in accuracy do not actually mean business gains after a certain point
- uncanny valley effect: if a model is too accurate and predicts what a user can do it turns a user off
- proxy over-optimization: optimizes a proxy and not the real thing. driving clicks instead of conversions.

*Modeling*

- setting up the problem is key
- how they consider different setups

- learning difficulty: look at how weel a very simple baseline approach does. Prefer problems where baseline approach does a lot better than random
- Data to concept Match: how well does out data match what we are modeling
- selection bias: is our data biased because of the way we are getting it

*Deployment*

- latency increases conversion. Machine learning models take time and so therefore decrease latency.
- sparse models with fewer parameters are quicker.
- minimze feature transformations

*Montiroing*

- we need to monitor the quality of our models

incomplete feedback: we do not know the true labels
delayed feedback: not seen until much later the truth

response distribution analysis: look at histogram of chart
- good model has peak at 1 and peak at 0
- if it is unimodel with a center in the model thats a bad model
- predicting one value a ton more than everything else might be bad.
- very noisy and non smooth distributions are a problem.
- difference in distribution between train and serve shows somesort of drift

this is nice because it can be applied to any classifier
- is robust to class distribution, addressed incomplete and delayed feedback.

*Evaluation*
- they use three groups rather than the traditional treated and not treated
- control group C, no change, Two treatment groups, invoke the model and make sure it was triggered but only in T1 do users see the change. this is basically to deal with elgibility criteria. Compare groups that were both elgible.

- this also gets rid of any latency effect from not having the model because the model was still called

1. A recurring theme in the paper is that traditional accuracy metrics do not translate to actual business impact. How can we bring business impact into offline evaluation? What steps can we take to make these two more aligned?

2. How do you measure the business impact of an increase in accuracy? what does it mean for an model to have an increase in accuracy of 5% in business context?

3. In the paper they highlight that the majority of ML research is about making marginal improvements to accuracy. They make an implicit argument that this research is not applicable to most real world implementations. Should more research be focused on the actual implementation of these things? How does academic research, even if focused in a different direction, still push industry forward?




## Thoughts

A lot of their model categories seem similar, content curation and user interface.

main focus of the paper is so much of Ml research is about squeezing accuracy up and up. A lot of what they are talking about is that, for actually use case this is bad.

we can make accuracy higher by making model more complex -> decreases latency. feature transformation -> decrease latency. cool how they address this by still serving the prediction. confused how they are divorcing latency from model performance. the two seem tied together.


histogram for predictions is pretty cool!

your mangum opus on academy in industry
- academia can get focused on things that do not also matter. It might be important to do this research but there should be more research like this. The large majortiy of research is divorced from application.

Academy can learn in so many other ways from being more efficient in terms of product planning measure more and being more transparent.

Industry can also learn from academy. It is important to do things that do not have immediate pay off. To research things that you cannot find have direct business value. They both can learn from each other.