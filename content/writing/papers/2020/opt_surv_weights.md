---
title: "Optimization of Survey Weights under a Large Number of Conflicting Constraints"
date: 2020-04-07T16:16:26-05:00
draft: true
---

[By Matthew R. Williams and Terrance D. Savitsky](https://arxiv.org/abs/1901.03791)

## Summary

normal weights are inverse probability

we have a Sample S taken of n individuals from a population U of size N.

- each person has a probability of being selected. These probabilites are correlated with the response of interest. You might be more likely to respond 1 if you are more likely to be selected. To account for this imbalance in probability of being selected we weight each response 1/pi, the probability of being selected.

Without these weights are estimates for our variable of interest for the population is biased. Direct use of these weights may be problematic though.

example, we might want to make range restrictions on our weight, not let it get larger than a certain value, we can make weights line up with population level info.

If we have a matrix X of possible weighting variables, we need to somehow pick which weighting variables to use. Different ways to do this.

Essentially they are trying to show that the space of possible weights becomes too large to find a closed form solution, we use to use optimization.Or it is possible the space is empty.

"The focus shifts from finding one optimal solution to finding one or more reasonable solutions which satisfy most of the constraints and restrictions"


motivating example is national survey on drug use and health

they show all the different variables they try to use as weighting, so complEX!!

* * * 

discussion of difference devianses / loss metrics. not sure why they call tehm deviances 

with l1 regression we can allows our target marginal to be a range!!!! THis is really good. THere does not need to be a specific target but a range of targets. show photo.

 * * * 

solution equations and solvers

* * * 

Apply to data set

As discussed in Section 1, there are other ways to evaluate weights and the impact on estimation; however, the purpose of this example is identify the space of achievable models (controls) rather than to compare the performance of models, which is a natural next step in an analysis.



## Thoughts

We do not need to find an optimal answer because it is too hard. We focus on finding multiple satisfactory answers. As problems become more complicated we have to get close and be clear about our assumptions. Makes it easier to try different things out and then evaluate. We should be more clear about our assumptions!

- often picking loss functions is tough but really difficult. need to think about business value when doing this. Why are certain things penalized and what is our desired behavior. 

- you should do this with things you know the answer to and then look at accuracy

- recasting equality constraints as penalties


