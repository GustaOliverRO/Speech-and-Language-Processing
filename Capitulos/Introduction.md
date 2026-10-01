# Introduction #

## What is a LArge Language Model ? ##

	- LLM is a computacional system that can predict the next
	word from previous words. That is, given a context or 
	prefix of words, a laguage model assigns a probability
	distribution over possible next word.
	
	Ex: "so long and thanks for ..."
			'...' = *all* or *everthing* (high probability)
			'...' = *of* or *wasn't* (low probability)
			
	- The language model is a large neural network that takes
	as input a *context*, the sequence of works seen so far, 
	and returns a probability for each possible next word;
	
	- Said up, the language models predicting or processing 
	*word*. This was simplificantions. In true, language 
	models use *tokens* as their input representation. A
	token is a word or word-part, and the firt step in 
	language modeling is to convert a sequence of word into
	a sequence of tokens. This process is call 
	*tokenization*, with the algoritm *BPE*;
	
	- *sampling or perplexity*
	
	- The performance of large language models is mainly
	 determined by 3 factors: model size (the number of
	 parameters), training dataset size (in tokens), and the
	 amount of compute used for training. So we can improve a
	 model by adding parameters, by training on more data, or
	 by training for more iterations. The relationships
	 between these factors and performance are known as
	 scaling laws. Scalings Laws explain why models tend to
	 get bigger, with both positive outcomes (more 
	 impressives performance) and negative ones (more expense
	 and use of natural resources like water and energy).
	 
	 OBS:  But very big models are also very expensive at
	 inference every time we prompt a model. So scaling laws
	 also explain why we often choose to instead train a 
	 smaller model and make it better by training for more 
	 time over more data.
	 
	 - *Pretraining*, is a processe of predicting words and
	 inducing knowledge, take a very very larg corpus of text,
	 and based a context, predicting a words;
	 
	 - Prompts, is a text strings that a user issues to a
	 langauge model to get the model to do something useful.
	 
	 -> Shannon GAME ?, if I play a Shannon game with you, I 
	 select a short text passage and you have to guess the
	 words in it, one by one, left to right. You first guess 
	 the first word. If you’re correct I tell you; if you’re 
	 wrong I tell you the correct first word, and you proceed
	 to guess the second word. We continue on this way, at 
	 every word you writing down the correct text so far, to 
	 help you predict upcoming words.

## Underpinnings: Neural Networks and Embeddings##

	Modern implementation of LM is two:
	- *Neural Networks*, machine learning systems that can be 
	trained from data, as the basic camputational mechanism;
	- *Embeddings*, vector that represent the meannings of 
	tokens and concepts inside the network;
	
	- A modern neural network is simply of small computing 
	units, each of which takes a vector (a list) of input 
	values and multiplies the values by some specific weights 
	and produces a single output value. What’s special about 
	neural networks is that they have a very efficient learning
	algorithm based on gradient descent (Chapter 4), for which 
	we’ll see more details in Chapter 6; (Open/Close-Weight
	
## Historiacal Context ##
	
	Symbolic Structure->
	
		 
## How Language Models are Trained ##

	- Pretraining
	
	- Instruction Tuning
	
	- preference Alignment
	
	- RL with Verifiable Rewards
	 
## Word Prediction Accuracy : Probability and Perplexity ##

	What is token overlap, about Proxy metrics
	
	
	 
	 
	 
	 
	 
	 
	 
	 
	 
	 
	 
	 
	 
