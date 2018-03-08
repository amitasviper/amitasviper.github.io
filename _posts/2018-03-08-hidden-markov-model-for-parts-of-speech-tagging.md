---
layout: post
---
Part-of-Speech tagging is a common sequence-taggin problem in Natual Language Processing. It is the process of assigning a single word POS tag to each token/word in the input sentence.
For example, for the input : `From the AP comes this story` the output of the tagger is `From/IN the/DT AP/NNP comes/VBZ this/DT story/NN`, in which the each POS tag escribes what its corresponding word is about. In this particular example,`DT` tag tells that `the` is a `determiner`.

There are numerous approaches for parts-of-speech tagging including rule-based linguistic, stochastic and machine learning approaches.

In this post, we will discuss the part-of-speech tagging using the Hidden Markov Models and Viterbi algorithm. Along with this, we will try to implement a basic POS tagger in Python.

We will divide our POS implementation in two separate phases:
<ol>
	<li>Learning/Training of the HMM Model</li>
	<li>Assigning POS tags for the unseen sentences(Testing)</li>
</ol>
Now, before actually
implementing these two phases, let's understand the two phases one by one.

<b>1. Learning/Training of the HMM Model.</b><br/>
Our HMM Model is composed of following elements:
<ul>
	<li>State Tranisitioning Probability Matrix (A) </li>
	<li>Word Emission/Observation Probability Matrix (B) </li>
	<li>Initial Probabilities: probability of each tag associated to the first word</li>
	<li>Hidden State of HMM i.e. POS tags like <code>DT</code>, <code>NN</code>, <code>NNP</code>, <code>VB</code> etc.</li>
</ul>

The entire working code can be found at the Github Repo [HMM-Part-of-Speech-Tagging][HMM-Part-of-Speech-Tagging].

[HMM-Part-of-Speech-Tagging]: https://github.com/amitasviper/HMM-Part-of-Speech-Tagging
