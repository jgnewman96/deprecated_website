---
title: "Declaritive Data Visualization with Vega-Lite and Altair"
date: 2019-10-31T15:51:05-07:00
draft: true
tags: ['ODSC', 'Data Viz']
---
Talk given by [Dominik Moritz](https://www.domoritz.de/) at Apple/CMU and [Kanit "Ham" Wongsuphasawat](https://kanitw.github.io/) at Apple

## Motivation

So what is declarative data visualization? As programmers we are used to imperative programming. Imperative programming is specifying how to do a problem. For example you say, put a red circle here and put a blue circle there. It couples the specification with the execution. In declerative programming we only specify what should be done. We would say map x and y to specific position, not how to max x and y. This allows us to seperate specificaton from execution. Now the compiler only handles how to do something, not what to do.

Using this approach allows us to focus on the data and the relationships in the data rather than how to visualize something. The speakers than talked through an example with matplotlib. Making a plot is easy in matplotlib, but once we start wanting to add any form of complexity, it gets really tough. Once we start trying to multiple variables and adding legends or titles, the code becomes quite unruly.

Declerative Data visualization is an alternative to matplotlib that should make it easier to work with data. Declarative data viz is inspired by the work of leland wilkerson, [the grammar of graphics](https://www.amazon.com/Grammar-Graphics-Statistics-Computing/dp/0387245448). But what is a grammar? It simply defines primitive building blocks that can be used to make data visualizations.

### Data Visualizartion Building Blocks

1. Data: The input to the visualization
2. Transformations: Different ways to transform the data (eg. filter, aggregation, binning)
3. Mark: A data-representative graphic, (eg. area , point, line, bar)
4. Encoding: A mapping between data and mark properties (eg. color, size)
5. Scale: Functions that map data values to visual values
6. Guides: Axis & legends that help us visualize scale

Using these building blocks the authors have created two libraries Vega-Lite (Javascript) and Altair(Python). These libraries using a grammar of graphics and the above building blocks. These bulding blocks make it much easier to build powerful and interactive data visualizations. ggplot which many people are already familiar with is a similar style library for R. 

Vega_lite: they do this by using Json 
- java script library 

then show examples -> much simpler than in matplot lib 

vega.github.io/editor 

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

