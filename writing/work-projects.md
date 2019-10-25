---
title: 'Work Projects'
date: Thu, 25 Jul 2019 21:51:28 +0000
draft: false
---

Nielsen 
========

My first job after completing undergrad is as a Data Scientist at Nielsen. Nielsen is a market research company that provides insight about what people buy and what media content they consume. I am a part of Nielsen's early career program focused on fast tracking individuals to leadership roles. The program consists of four six months rotations for a total of two years. Below is a description of all of my rotations, what I accomplished during them, and what I learned from each rotation. During my time at Nielsen I have also been leading the Machine Learning Community of Practice. I describe a couple of initiatives I have worked on as part of the ML CoP.  During my time at Nielsen I have focused on building sustainable solutions and modernizing how we work. 

Rotation 3: Digital Pipeline Development
========================================

### _Project Description _

Nielsen is in the process of transforming how we build our products. We are a ninety five year old company that is not technologically native. We are working on building products that are more maintainable and reducing the amount of work that we duplicate. Data science in particular is undergoing a large transformation within Nielsen. 

Previously, Data Science sat very far away from the final product and a large portion of the data science organization did not have the technical skills to build reliable technical products. The data science organization was very much seen as the place where research happened, but then technology would actually build products. There also would be very minimal day-to-day interactions between data science and technology. Data science would work on a project for a long time and then throw it over the wall to technology. 

Software development is never going to be Data Science's strong suit. The people who are in Data Science have different skill sets and have strengths in a different field. But we can work to develop better engineering skills within Data Science and have data science writing code that goes into production systems. I am working to improve how data science contributes products for the digital and advanced tv team. 

Moving data scientists closer to the product involves changing how we work on a couple of different fronts. One part of it is working with data scientists to improve their engineering skills. Another part of it is creating internal systems that better facilitate development. Another part is working with tech to figure out the best division of labor between the two separate organizations. There will not be a singular panacea that solves everything, but rather we have to work with lots of different individuals to figure out how we can put them in the best situations to succeed. 

### _My Contribution_

*   One of my big contributions this rotation is rewriting and automating our digital adjustment factors process. Digital adjustment factors is a process for how we adjust our digital numbers based on some known biases in our data. This process used to be highly manual with all of the code being stored in notebooks and someone having to run it manually. I have done all of the following things with the code in an effort to improve this process: 
    *   Taken large SQL queries and turned them into modular testable PySpark 
    *   Written both unit and integration tests for all of our code 
    *   Orchestrated the code using Airflow 
    *   The process is now callable through an API
*   While re-writing the adjustment factor process is a nice win, a large focus has been on using this process to develop learnings that can be used for future projects. I have written extensive documentation about how I automated this process and what best practices would be for future developers. While I was working on this project the beginning was quite slow as I was learning a fair amount. After that I was able to develop quite quickly. The hope is that by using my documentation other developers will be able to have a high velocity in their projects from the beginning. 
*   During this rotation I have also identified that there is a large gap in how we document and track models. I believe that is gap exists across the entire data science industry and not just within Nielsen. All models involve the data scientists making many different assumptions and decisions. We should make the data science process one that is a lot more transparent and accessible to all. I have been working with Nielsen to develop better practices documenting our data science work. 

### _What I Learned_

*   This rotation was the first time I had to write code that was directly going into one of our existing products. I have had a fair amount of experience writing code with tests, but most of previous experience was writing unit tests. This rotation I learned how to identify and write integration tests. I learned how to incorporate system monitoring into what I am building and how to build something that you can easily debug and identify what is causing issues. 
*   In this rotation it was very important for me to take what I was learning from one process and identify how it could be applied to many different process. I had to continually push myself to think outside of the scope of my project and focus on larger structures. I found that doing this big picture thinking was very helpful in doing better work locally. Connecting my work to larger processes helped me better understand the context of my work and make me more motivated. 
*   I had previously tried to take aspects of agile and incorporate them into my day-to-day but this was the first time I truly worked in an agile framework with sprints and the agile ceremonies. One of the places I see people failing the most with agile is too closely trying to follow the letter of the law. Agile is much more a way of thinking about work and planning rather than an exact script to follow. It is not about doing everything by the book but finding which parts of agile help you the most. 
*   A large part of this rotation has been working with many different teams across both data science and tech. I have had to understand how different people have found their own ideal workflows and identify the commonalities between them. It can be really easy to look at how different people do different things and recognize all the differences. While there will be lots of differences and those are important, we want to let teams and individuals locally optimize, it is just as important to identify the commonalities.  The places where we find a common structure are the places where we can use tools or a structure to help people focus their time. We want people focus their time not on the commonalities but the nuisances and uniqueness of their individual space. 

Rotation 2: Bayesian Inference for Ratings 
===========================================

### _Project Description _

Nielsen is best known for their linear television ratings which estimate the number of people who were watching a channel at any time. This information is estimated using a representative panel of households all across the United States. Households in Nielsen's Panel report all of the television that they watch. Each household's viewing is weight based on its demographics to ensure that the viewing is representative of the population. 

While this approach gives an estimate of the number of people who are watching a given channel, there are some problems with it. When there is a show that is very widely watched, such as the Super Bowl, Nielsen's methodology does a good job of accurately estimating the viewership. But for shows with less viewership such as more niche shows or shows during the day time, Nielsen will regularly have no one in the panel viewing those shows. We can expect that the rating is not actually zero, but because the panel does not account for everyone it does a bad job estimating these low viewership shows. 

The computational modeling team is exploring a new approach to calculate ratings. The team is exploring using Bayesian Inference to combine panel data with other data sources to create a more accurate estimate of TV viewership. 

### _My Contribution_

During my time on the computational modeling team my work focused on building tools that let the team iterate faster. I built a couple of different libraries for the team that allowed them to incorporate new data into their models and evaluate their models. I focused on reducing the amount of code that team members had to write and letting them focus on modeling decisions rather than engineering. 

*   I built a library that allowed the team to easily pull third party data. For example this library allowed the team to easily pull census data or weather data. This made it easier for the team to incorporate other data sources into their modeling process.  
*   I built a visualization tool that allowed the team to systematically evaluate their models. This visualization tool consisted of a user interface that allowed the team to understand quickly the success of their models and where their models were failing. The interface also allowed the team to explore feature importance and how different features were driving model output.  
*   The last tool I developed was a library that wrapped the model training process and made it seamless to publish a new model and visualize it. This made it easier for the the team to train a model, visualize it, come up with improvements and then train a new model. 

### _What I Learned_

This rotation was much more structured than my first rotation. I was working with a team that had already been working on a problem and had a defined direction. I was building software to help enable the team. This was the first time I built software that other people were going to use. 

*   I learned a lot about how to design software that is extendable and that people will actually use. I learned the real power of object oriented programming and how to use abstract classes. I learned how to make software diagrams and create user stories. I also got first hand experience with the necessity of focusing on your user and involving them in the creation process (how to get feedback from users and incorporating that as I develop). I also learned about how to make different parts of software independent and have them interact through contracts. This rotation taught me a lot about how to build software that people will actually use.  
*   I also learned about how to think about problems in a bayesian way. While I was not doing as much model development, I still had to understand how the team was approaching the problem and what were the advantageous of the new methodology. I learned about how MCMC (markov chain monte carlo) and SVI (stochastic variational inference) work. I really enjoy thinking about problems in terms of a data generating process now and using structural models rather than pure machine learning. 
*   A big part of being on the computational modeling team was that we were working in a new space. This meant a lot of reading of recent papers and learning as we go. It is a very different process to apply something that is well established then to apply something that is still being developed. While at times it was difficult to be building something where best practices or approaches had yet to be established, it was quite exciting. 
*   The computational modeling team was based out of New York while I was working in Chicago. Through this process I learned how to best work with a remote team. It is so important to be friends with the people you work with and that is difficult when you are not seeing them  regularly. I learned how to put time into forming remote relationships and to learn about my teammates lives outside of work. 

Rotation 1: Non-coop estimation 
================================

### _Project Description _

Nielsen receives data from retailers about all of the items they sell. For example, Walmart sends Nielsen all of the products sold at each store in the past week. Brands, such as Johnson & Johnson, use this information to see how much of their product is being bought. Some retailers do not send Nielsen their data. We will refer to these retailers  as non-cooperators. Non-cooperators do not send Nielsen their data because the majority of the items they sell are from their own brand. A retailer that is a good example of this is Trader Joe's. Non-cooperators limit Nielsen's ability to give our clients accurate information about market share because there is part of the market that Nielsen cannot see. My project was to develop a new methodology for estimating the sales of non-cooperators. 

### _My Contribution _

I developed a new methodology that had a 20% improvement in accuracy over Nielsen's old methodology. Estimating non-cooperators' sales is a particular difficult task because there is good reason to believe that non-cooperating stores are fundamentally different from stores that do cooperate. My methodology was based on the principles of how kernel regression works. The methodology works in the following two steps:  

1.  Use different features to assign a similarity score between each store 
2.  Project a given store's sales using a weighted average of similar stores. 

### _What I Learned_ 

This rotation involved a lot of learning for me. It was my first foray into the business world. My project was completely open ended. I was tasked with a business problem and asked to solve it however I wanted to. I learned a lot about how to build a model from scratch, how to define success criteria and how to work efficiently. I discuss some of my main learnings in detail below. 

*   Model acceptance is more complicated than just maximizing model accuracy. Models are just one part of a larger complex system. Verifying that a model is worthwhile involves understanding the role that a model plays in that larger system. We have to take into account model simplicity, model explainability as well as how the new model compares to the previous approach. This project was particular difficult because we did not have a truth set that we could use to measure model accuracy. We had to develop a proxy for model accuracy. Validating a model involves using lots of evidence besides just error rate. 
*   Building off of that point, I learned a lot about how being a good data scientist involves a lot more than being good at building models. It is of critical importance that a data scientist understands the business context and the role that their model plays in it. You have to be a good communicator and understand where different people are coming from. It does not matter if you have built the best model in the world, if it is solving the wrong problem. Building good models is only one skill that determines if you are a good data scientist. 
*   This rotation also taught me the importance of understanding our data before beginning the modeling process. Even if a model should work in theory, if there is no signal in the data, even the best model will not be useful. Throughly exploring our data before hand and identifying the key relationships or structure is crucial. If you believe a certain modeling approach will work, find evidence in the data. Use the data to show that the assumptions you are making in the model building process are good ones. All models involve some assumptions. It is important that those assumptions are supported by data. 
*   This rotation was the first time I was coding for the majority of the day, every day. I developed much better coding habits. I learned how to write good documentation for both myself and others. I also now understand how to better plan modularity in my code. 
*   Meetings can be your best friend or your worst nightmare. Meetings are opportunities to hear other's opinions and get feedback on your work. Truly two of the most important things you can do. Meetings can also suck away all your time and zap your energy. A couple of tactics I have found that make meetings run smoothly: 
    *   Clearly state the purpose and agenda of each meeting 
    *   Send materials for the meeting ahead of time 
    *   Make sure that everyone's voice is heard and that everyone is contributing. Each person should be at the meeting for a reason. 
    *   Always take meeting notes and send them as a follow-up afterwards 
    *   Meetings are places were decisions should be made and everyone should have action items after a meeting. Make sure actions items are clear and understood. 

Machine Learning CoP 
=====================

### _Project Description _

*   group to help bring machine learning, learnings to all parts of the organization 
*   hosts webinars, and really just be a first point of contant for all things machine learning 
*   website with resources, experts, guides 

### _My Contribution_

*   study groups --> wanted to facilitate learnings across the org, this was my biggest thing 
*   coding club for leaders in the org, putting together presentations for them to know technical things

### _What I Learned_

*   How to stay motivated even when it seems like things are not happening 
*   How to recognize that there are different users with different needs 
*   You do not have to do everything yourself it is important to partner 
*   The importance of setting direction