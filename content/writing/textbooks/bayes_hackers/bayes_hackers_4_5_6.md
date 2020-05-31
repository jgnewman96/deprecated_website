---
title: "Bayesian Methods for Hackers: Chapters 4, 5 and 6"
date: 2020-05-06T13:19:28-05:00
draft: True
tags: ['Data Science' , 'Statistics']
categories: ['TextBooks']
katex: true
---

four, five and six each have one idea really and then types and tricks

best thing about this books is really the examples.

## Chapter 4

Law of large numbers

pretty obvious but when we start looking at large datasets we forgot.

For example a large dataset but low numbers in some regions.

For example low numbers in states.

Then we treat all inference the same. Logisitic regression model. There are CI's on variables but we usually do not use the CI

This is why uncertainity is so important

## Chapter 5

loss functions

we can incorporate other loss functions. Being able to incorporate a loss function is so important because it allows us to treat different types of errors differently.

Rarely is just a standard MSE actually what we want in the real world. Loss functions allow you to tie things to business context. Normally it worse to over predict or under predict. or Over predicted by certain margins does not matter but after a certain point it becomes really bad. Having a custom loss function is really important.

Example here is stock market gains. Getting the sign right is very important.

## Chapter 6

picking our priors
subjective vs objective. How do we incorporate information.

getting priors from experts. Link the other paper I read. Really important in the business context to get knowledge from domain experts

[Conjuge priors](https://en.wikipedia.org/wiki/Conjugate_prior#Table_of_conjugate_distributions)

[Wishart Distribution](https://en.wikipedia.org/wiki/Wishart_distribution)

penalized linear regression is just a prior


