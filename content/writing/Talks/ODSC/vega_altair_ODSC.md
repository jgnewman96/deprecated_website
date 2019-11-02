---
title: "Declaritive Data Visualization with Vega-Lite and Altair"
date: 2019-10-31T15:51:05-07:00
draft: true
tags: ['ODSC', 'Data Viz']
---
Talk given by [Dominik Moritz](https://www.domoritz.de/) at Apple/CMU

Kanit "Ham" Wongsuphasawat at Apple

What is declarative data visuilzation 

traditional programming is imperative 
- specify how to do something 
- put a red cirle here and blue circle here 
- couple specification with execution 

declaritive 
- specify what should be done 
- map x and y to postion encodings 

seperate specification from execution, 
compiler just handles how, not what you want 

this allows us to focus on data and relationships rather than incremental 

example with matplot lib 

iris = df.read_csv("iris.csv" )
plt.scatter(iris.petallength, iris.sepalwidth )

trick when we want to do another thing 
- add another variable with color is tough 
- color map is really tough 
- just adding species of color is tough 

adding legends and titles is tough which matplotlib 

- it can be powerful but there are tideous steps 

enter declerative data visualization 

leland wilkerson, the grammar of graphics 
- inspired from this work 

what is a grammar? a grammar is just defines primitive building blocks 

# Data viz concepts 

- data: input to the visualization 
- transform: filter aggregation binning
- Mark: data-representative graphic, area , point, line, bar 
- Encoding: mapping between data and mark properities : color size 
- Scale: functions that map data values to visual values 
- Guides: axis & legends that visualize scale 

With this pile of building blocks they create Vega-Lite: A grammar of graphics 
- ggplot embodies a similar idea for R 
- they want to make it interative and multi view graphics 

Vega_lite: they do this by using Json 
- java script library 

then show examples -> much simpler than in matplot lib 

vega.github.io/editor 

python wrappers for vega-lite called Altair 

rest of workshop actually shows altair in practice 

https://github.com/vega/vega-lite-tutorials

the rest is done in notebooks

they show how easy it is to do things and make things that are really hard in matplot lib 

can call to json method on the altair to use it on the website 

can easily put the visualization on a website 

can layer two plots with just using a plus and it actually formats it for you in a nice way 

## My thoughts 

visualization is so hard and adding the structure of this grammar to it is so important 
- histogram example --> level of abstraction 
- might make one thing harder, but generally makes everything easier 

