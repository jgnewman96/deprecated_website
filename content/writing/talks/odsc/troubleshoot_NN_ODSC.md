---
title: "Trouble shooting Deep Neural Networks"
date: 2019-10-31T11:51:11-07:00
draft: true
tags: ['ODSC' , 'Deep Learning']
---

Talk given by [Josh Tobin](http://josh-tobin.com/) works at Open Ai and [Full stack Deep Learning](https://fullstackdeeplearning.com/)



troubleshooting is the single hardest part 
- even the best practitioners spend a long time doing trouble shooting 

the fast majority of what good people do is following a desicion tree

present the decision tree that he uses

Xkcd machine learning stiring the pile of shit around

80-90 percent of your time actually goes into debugging and tuning 
and then 10-20 percent is derviing math or implementing things 

but why is troubleshooting DL so hard 
- suppose you cant reproduce a result
- tryting to reproduce a resnet paper 
- but your lose is actually worse so if your model is worse what do you do next 

hard to tell if you have a bug, but in deep learning bugs are silent, in software engineering bugs are not silent 

lots of possible causing for having bad performance - bad hyper parameters, 

model performance is very sensitive to hyper parameters 

* * * 
strategy for DL troubleshooting 

we need to have a mindset in mind
- the mindset is we need pessisimism 
- hard to disambiguate errors 
- way to be pessimistic is start as simple as possible 
- gradually we ramp up complexity 
- allows us to be sure if our performance changed why it changed 

first thing to do is start simple -> simplest model and data 

a: chose simple archtecture 
    - choose a simple architecture to start 
    - demystifying architecture 
    - images -> start with le net then move to res net 
    - data is sequences -> use LSTM and then slowly move to trasnformer
    - other -> fully connected neurl net with one hidden layer, where you go after that is problem dependent 

what about multiple input modalities --> two images and sentence 
    - does sentence apply to images 
    - map each into a lower dimenstional feature space 
    - for images conv net and lstm 
    - then you flatten the output 
    - concatenate 
    - then send it through a fully connect layer to get an ouput 

b: use sensible defaults 
c: normalize inputs 
- do not pass raw images, substract mean and divide by various 
d: consider simplyfing the problem 
    - use a subset of the data set 
    - if you have lots of classes start with just a subset 
    - create a simpler synthetic training set 

second: implement and debug 
a) get your model to run
    - most common bugs 
        - incorrect shapes for tensors 
            - a lot of the libraries will silently broadcast tensors without your knowledge 
        - pre-processing inputs incorrectly 
        - incorrect input to your loss function -> softmaxed outputs to a loss that expects logits 
        - forgot to set up train mode for the net correctly 
            - toggling training/eval, batch norm dependencies 
        - numerical instability - inf/Nan 
            - often stems from using an exp, log, or div operation 
            - use off the shelf softmax rather than writing your own 
    - general tips 
        - use a light weight implementation: minimumu possible lines of code for v1, less than 200 lines of code
            - each additional line is new change for bugs 
        - use of the shelf components where you can
        - build complicated data pipelines later,
            - should not spend the time doing this when you are still debugging 
            - start with a dataset you can load into memory 


b) overfit a single batch
    - catches a huge number of bugs 
    - drive the error of your model error to zero
c) compare to a known result
    - see if your model is comparing as well as other people think it should 
    ideal: 
        - official model implementation evaluated on a similar dataset to yours 
        - you can compare your code to tehir code 
    less ideal: 
        - unofficial model implementation 
        - a lot of repos will have bugs in them
        - do this but do it cautiously 
    even less ideal 
        - results from a paper with no code: 
    underated: 
        - compare to super simple baselines 
        - the average of outputs 
        - linear regression 

third: evaluate model -> decide what to do next
- bias variance decomposition 
- look at the gap between train, valid and test 
    - tell us why our model is underperforming 
    - gap tran and val is how much we are overfitting 

test error = irreducible error + bias + variance + distribution + val overfitting 
- tells you which improvements to prioritize 

we assume train, validation and test all come from the same distribution 

training data could be from during the day, but testing could be from the night time scene 

how do we handle this, using two validation sets, one from training distribution and one from test data 
- held out data from training and held out data from your test 
- the difference in these two is the error from distribution shift 

fourth: improve model or data 
a) address under-fitting 
    - ranked from try first to last 
        - make your model bigger, wider or deeper 
    - reduce regularization 
    - error analysis 
    - choose a different model architecture 
    - tune hyper parameters 
    - add feature 
b) address over-fitting 
- ranked from first to last 
    - add more training data
    - add normalization 
    - do data augmentation 
    - regularization 
    - error analysis 
    - choose a different model architecture
    - tune hyper parameters  
    - early stopping 
    - remove features 
    - reduce model size 
c) address distribution shift 
    - training distribution does not look like test 
    - hard to get data from test distribution 
    - we learn it is not working well in real world 
    - try from first to last 
        - error analysis 
            - look at error and prioritize places for more data collection 
        - synthesize more data rather than collect it 
        - domain adaptation techniques 
            - new researach not quite advanced enough 

    error analysis 
        - look at errors on train-validation set and test-validation 
        - classify them manually 
            - for example hard to see pedestation, 
            - reflection 
            - night scenes 
        - error analysis by types of error 
        - what percentage are coming from each category 
        - how much error do they introduce, how could we fix it and what are the potential solutions 
d) re-balance datasets 
    - periodically check on held out test set

fifth: tune hyper parameters 
    - so many potential hyper parameters 
    - learning rate, batch size, 
    - start with ones you know matter, batch size and learning rate 
        - if you do not get where you want through this approach look at others 
    coarse-to-fine random searches 
        - look in a large range 
        - then narrow in on narrow regions 
    - consider bayesian hyper-parameter optimization 
        - can be hard to implement 
        - only invest in this as your code base matures 

What do you need to start the prroblem 

even before doing this, we assume you have a 
data set and 
a metric you are trying to improve 

you need target performance based on human level performance, published results or previous base line 

example is clasiffying whether or not their is a pedestrain in the image 

simplest place to start --> subset of images 

use lenet 

adam optimizer 

a lot of problems come from regulariztion --> start without it and then add it back in if you need it 

lloks at these errors with the pedestation example 
- both underfitting and overfitting

#### conclusion 
why is this so hard 
- due to many competing sources of error 
- you have to be pessimistic, make it an iterative provess , start as simple as possible and then add complexity 
- following the steps talked about today makes this easier 

longer verions on his website http://josh-tobin.com/troubleshooting-deep-neural-networks.html

## My thoughts 
- really good structure to to talk, broke it down into itemized parts

- good framework for problem solving in general 

- he essentially used topic sentence, intro at the beginning of every section and summary at the end of every section 

- one example underlying everything he returned to, talked abstractly and then returned to the example 