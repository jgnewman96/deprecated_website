---
title: "AI Neuroscience: Can we understand the neural networks we track?"
date: 2019-10-31T10:55:26-07:00
draft: true
tags: ['ODSC', 'Deep Learning']
---
 Talk given by Jason Yosinski works at uber ai labs and recursion pharmaceuticals

 We train neural networks but often do not understand how they work 
 - examples of deep learning --> alpha go 
 - robot gait learning, teach a robot to walk 
 - example from his work, show a robot learning to walk 
 - reinforcement learning and robtics also great movement in language 

 machine learning progress over time 
 - more computation 
 - more data 
 - these two factors make better models 

 but scientific understanding is fundamentally disconnected from progress 

 if a computer becomes two times faster we do not understand two times as much

 at our current region, we are building models that are more powerful than we understand
 - can we keep our understanding closer to our progress 

 lets look at example from computer vision 
 - alex next, can be code in like ten lines of keras 
 - define the size of layers, the relu between them the intilization 
 - not the model itself, but the skeleton 

 - the model is actually a tons of number, the values in the matrix 
 - at the end we have 60 million numbers in the right spot 
 - but how do we understand what these numbers are 
 - it is hard, but not unimportant 


 - lets understand middle of network, we under stand images at one end and classification at the other end. 

 simple approach put images in and plot stuff 

 deepvis toolbik they built at his website. yosiniski.com 

 - look at the alex net strcuture and correspond what he is talking about

 first look at first conveulational layer

 tool that takes an image and runs it through alex net, shows the feature detectors, looks for a pattern detector everywhere in the image. 

 photo of him and shows the white to black or black to white firing 

looking for patterns in pixel space and if it sees them it is firing 

 second layer looks for patterns in the previous layer, not in the pixel layer 

 by stacking these thing they slowly see more and more space. first one sees things in 11 x11 space, but as you stack the layers they can see more pixels and they can see more abstract stuff 

 - first it sees pixels, then edges and then higher and higher levels of abstraction 

 look at the fifth conculational layer 
 - features should be highly abstract or , there is one section that is a face detector, shows examples of photos in the room 
 - look at the images that cause a neuron to fire the most 
 - conv 5 has 256, one neuron that finds text, one that does face 

- why does it learn these features? we never taught it to learn these features, we told it what to learn at the end 

why does it learn text? because it has to learn these abstractions to help with its  task 

seatbelet example - gray stripe, but these are everywhere 
- it has to learn seatbelt and beneath face

- learns to detect faces so it can learn to detect seat bealts 

text helps us learn the category camera lense 
- if it calls everything thing a black circle a camera lens it will fail 

- but black cirlce plus text could be a camera len

we know understand a little bit about the middle layers 

we only looked at a couple neurons in the middle, but it would take forever to just understand one feature detecotr, but understand all the neurons would take forever and be hard 

* * * 

frustrated but entranced -> ask the network to paint picture of gorilla 
- why does a network think something is a guerilla 
- the hair, the background as grass, the face 

come up with a method where a network tells us what a guerilla is 

start with a pixel of white noise feed it through the network, it says basically it could be anything 

actually using back prop compute things that would get us more guerilla --> move the white noise image in pixel space closer closer to guerilla 

now we go forward guerilla should be more likely, and then we should eventually get a guerilla 

did this, we did not get guerilla looking thing 

but netwrok says with very high proability it is a guerilla

wrote a paper about how this failed 

science if it fails its a paper, in engineering if it fails you failed 

deep networks are easily failed 

use regurilize to shrink the image space, do not have any pixels be too extreme 
- combine a bunch of regurilizers, l2, l1 and spatial smoothness regularizer, we are getting better results 
- example with hartebeest and school bus 
- with hartebeest does not learn the hooves, lots of animals have hooves, but it does learn about the horns and shape of the top of it 
- school bus, looks for patterns of yellow and the windows and some of the wheels

we kind of know what the thing is learning, regularizer is a prior to keep images in a region 

but we can actually just have two networks, plug and play generative networks, 
- we have a panter network that says image looks real or not and then image that says what it looks like, so a cheese burger 

first paint for if it is realistic image and then make it look like a specific class

change the input to being an caption --> generate a photo from a caption

-- the way we collect the data biases the model, but not caring about the smaller things in the network 

what if we could replce a network with a brain? we cannot back prop through a brian? 
- group in harvard and japan, showed images to monkeys 
- saw what neurons fired for monkeys 
- showed random photo to monkey and then create a new photo to monkey to slowly get what the monkey is actually trying to see 
- get a photo the excites that neuron even more 
- 

LCA: loss change allocation for neurel network training 

algorithm trained on mnist
- when we train it all wee see is the loss curve going gown 
- but what is actually happening 
- we just see a scaler going down 

LCA -> anytime we see a change in the loss which parameter is training 
-- offers a very rich visualization of training 
- we can see which parameters are learning 
https://arxiv.org/abs/1909.01440

three things we learn 
- noisy 
- some layers loss
- micro learning is synchronized 

gives us a lot more visibility into traning 

if we bin parameters into helping, hurting and no change
- only 50 percent of parameters actually help, some parameters hurt 
- training is very noisy 

we can look at how much each layer help, different layers help more or less 
- some layers go backwards 
- layers are oscillitating 
- some layers beat the other layers and then layers miss out? 

all three layers make a jump in learning all at once 

slides s.yosinksi.com/odsc.pdf


 ## My thoughts

  what is a neuron and what does it men for it to fire? 

  Iterative process of looking into, checking something, then doing another, then checking that out 

  try and figure something out, then debug further, then try the next thing 

  layers going backward seems odd, maybe are defintion of help is wrong 
