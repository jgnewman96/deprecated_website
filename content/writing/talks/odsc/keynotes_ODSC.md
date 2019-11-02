---
title: "ODSC Keynotes"
date: 2019-10-31T08:22:50-07:00
draft: false
tags: ['Machine Learning']
categories: ['Talks']
---

## AI Lifecycle Model Management: Monitoring for Risk, Bias and Fairness 

Talk given by [Sepideh Seifzadeh](https://community.ibm.com/community/user/people/sepideh-seifzadeh1)

Why do we care about data regulation?

- increased collection of data
- low cost storage
- Machine Learning capabilities have increased --> doing more things , more unintended consequences or harms

Why is there going to be AI regulation 
- how is it going to protect us from harm 
- could regulation be bad, could it stifle innovation, regulation has some harms and some nefits 
- should we incremental make laws or make a new set of rules

When AI makes a mistake who do we blame?  who is liable for self driving care mistake

example of Compas, give a score to the defedant before the trial date, should we put them in jail or not, algorithm gave them a score, algorithm was biased to have more false positives for black defedents 

So what are the solutions? 
- IBM is a leader in this space 
- AI fairness 360 

ML lifecycle

Collect data --> organize data --> analyze the data --> infuse the data 

importantant to continue to montior the model

IMB has partnered with red hat to solve this 

Cloud Pak for data

Shows an ended to end lifecycle using IBM tools the whole way 

### my thoughts 
maybe i struggled with it because I have been thinking about this space a lot of late 

how do you combo high level stuff with actual meat, like yes AI is going to be regulated, AI is growing, people are using it more, we get that 

I know it is hard to do a quick 30 minute conversation, but this actually did a disservice to how hard this is, and how nontrivial it is 

In a quick chat you have to get to big ideas that made people thing 

This was a sales pitch 

Interesting to see that this is how IBM is marketing themselves now


## AI and Security, Lessons, Challenges and Future Directions

[Dawn Song](https://people.eecs.berkeley.edu/~dawnsong/) founder of oasis labs 

deeep learnings has made advancements, alpha go, personal assistants

in security attacks are increasing in scale and sophistication 

mirai botnet, Iot attack ddos, also large data breaches 

we should consider the presence of an attacker as we deploy deep learning --> as we automate more systems it makes it easier for attacks to have more power. 

How can attackers attack 
- they can attack integrirty, cause a system to produce incorrect or specific outcomes 
- confidentiality -> get sensitive information

AI can also be used in to create attacks, 

we need to develop security AI systems

consider self driving cars --> exampe of how you can mess with stop sign if you put tape on it and trick the driving car, can cause misclassification into speed limit sign 

important to make learning system robust to attacks 

example: Visual question & answer 
- input as image and question and then generate answer 
- we can add noise that does not change anything to the human 

- if it can be attacked we did not make a good model

can even be done with reinforcement learning and creating agents 

whitebox attacks, attacker has access to the actual model 

but there is also blackbox attacks that are very effective 

confidentiality, learn something from the data
- differential privacy

-- users having control over their data, distrbuted ledger and smart contracts 

extracting secrets from training data, memorization vs generalization, link to the [morning paper write up](https://blog.acolyer.org/2019/09/23/the-secret-sharer/)

Instead we need to train a differential private model, same level of accuracy, but attacks are no longer 

what is dfferential privacy? 
- look at a data set with one data point more than the other 
- an algorthm is private if the computation results is essentially the same from the two results 
- by looking at the results an attacker cannot tell if Joe's data point is in the data set or not

It can be hard to deploy algorithms that are differentially private
- usable by non-experts 
- integration with exisiting environment 

developing techniques and tools to deploy differential privacy 

oasis labs, they have been putting all of these things together, kera is an app to improve data siloing in medical research 

many important question to still answer 
- building better systems 

security is a large challenge that requires community effort 

### my thoughts 

AI and ML is just a tool, anything can be done with it 

the key is how when you automate something you give more control, like if you have humans doing it, it is harder, person on the street corner versus posting on the internet

these systems are not intelligent they arte just doing apttern recognition 

this type of work is so important, but to me the conlusion should not just be, lets think more about security they should be broader 

how does focusing on these niches maybe lead down the wrong path? yeah lets continue on the current path and make it more robust rather than these are a lot of concerns that show us hey maybe we should go down a different path 

It is interesting to think about what is the purpose of the keynote talks. maybe these keynotes are just about making data scientists more cautionary about what they are doing 


## Getting Specific About Algorithmic Bias

[Rachel Thomas](https://www.linkedin.com/in/rachel-thomas-942a7923)

facial recognition, gendershades.org 
- performs a lot worse on dark skinned women 

amazons facial recognition matched 28 members of congress to mugshots, more for congressman of color 

harini suresh and john guttag - a framework for understanding unitended consequences of machine learnng 

face recognition is representation bias, training sets had white men in them more 

evaluation bias --> bench mark data sets having light skinned men 

we can create more representative data sets -> part of dender shades , consider consent when creating datasets 

compass algorithm - false positive rate for black defedants was twice as high - 40 percent of black defedents who were labeled as high risk did not re-offend 

same peformance with a linear classifier with three variables 

race was not an input into compass algoirthm, but it was found as a latent variable, we have to be careful of this 

feedback loop, when a model controls the next round of data you get, you implement a model and then it affects what data you get 

reccomendation systems predict what content users like but then also affects what they actually see

historical bias -> getting more data will not mitigate the compass thing, we have historical incarciareted higher rates of black people. 

suresh et al 2019 for defintion 

it is so important to work with domian experts, work with people in the legal system and those actually impacted by it. 

third case study: online ad delivery 
- latanya sweeney , google her name and then ask if she has been arrested 
- neutral sounding adds for kristen lindquist, but she actually has three arrest 
- this pattern held names for black people had these worse ads 

company said there were allowing you to post both and then people did A/B testing to get the one people will click on more

AI ethics concerns are about human rights 
- anil dash there is no tech industry any more 

we need to consider what civil and human rights we want to protect 

idea of data being biased is just too generic, when you actually want to get deeper 

sendhil Mullainathon and ZIad Obermeyer - who is most likely to have a stroke 
- most predictive is prior stroke 
- cardiovascular diese 

- accidential injury
- benign breast lump 
- colonoscopy 
- the last three should not actually be predicitve 

we are not actually measuring a stroke 

we are measuring do you have symptoms go to the doctor, get tests and recieve a diagnosis

so essentially if you use healthcare more, that is what those are measuring, this is a form of measurement bias, we are using aproxy to what we care about and that different is important 

Historicial Bias
- when doctors are shown identical files much less likely to give a helpful reccomendation for black people
- responding to fraiglist apartments with black name 
- when bargaining for a car, black people are offered higher prices 

-- this historical bias is everywhere 

why does algoirthmic bias matter --> humans are biased too 

machine learning can ampelify bias

algorithms are used differently than human 
- people are more likely to assume algoirthms are fair 
    - with people we recognize they are subjective 
- algorithms are more likely to be implemeneted with no appeals in place 
- algorithms are used at scale 
- algorithms at scale 

towards some solutions 
1. analyze a project at work/school 
    - number of frameworks, she has her own 
    - when the implication is not to design technology 
    - should we even build this 
    - sometimes the answer is just not to build something 
    - what bias are there in the data? all data is biased so important to see what data there is, data sheets for data sets 
    - can the code and data be audited, open source 
    - error rates for sub-groups? 
    - accuracy of simple rule based alternative 
    - how do we handle appeals or mistakes 
    - how diverse is the team that built it 



### my thoughts

love her calling out the other researchers 

she does this so well examples and depth, but also keeps things at a high level 

