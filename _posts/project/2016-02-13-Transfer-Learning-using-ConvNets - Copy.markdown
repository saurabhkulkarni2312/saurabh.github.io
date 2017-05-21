---
layout: project
title:  "Music Generation using RNN"
date: 2014-04-25 16:54:46
author: Saurabh Kulkarni
categories:
- project
img: rnn.jpg
<!--carousel:
- single01.jpg-->
tagged: Python, Keras, Tensorflow, Recurrent Neural Nets
---
### Objective
Build a character level RNN to learn and generate Music

### Project Details
**Aim**: In this problem, we try to build a RNN to generate music in abc format. 
A basic RNN is trained using characters extracted from a music dataset provided to you and then run
the network in generative mode to "compose" music.

**Data**: A set of tunes in ABC format

**RNN**: Time series data have temporal dependencies. ConvNets are unable to model some tasks where the data have temporal dependencies. For these sequential
relationships Recurrent Neural Networks (RNNs) are used. RNNs are typically used for machine translation, NLP and 
word prediction etc. You can train RNNs with 

**Approach**:
We first train the RNN to learn the structure of an ABC file notation. In the training stage, the network takes the ground-truth character of current step as input and predicts the
next character. Then the next character is used as input, and it is trained to produce the next character. That is, the network learns to predict the (n+1)th character from the
n-th character. A single hidden layer was used for this problem.

In the generation stage, the idea is to "prime" the network with a sequence, and then let the network run on its own, predicting the next character, and the using the network’s output 
as the next input. This way the network "composes" it's own tune. 