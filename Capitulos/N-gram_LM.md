# N-gram Language Models
	
> Language Model (LM) is a machine learning model that predicts
upcoming words. More formally, LM assigns a **probability** to each 
possible next word, or equivalently gives a probability 
distribution over possible next words.
> Obs: A language model, because use the probability, can help 
users select the more grammatical variants. Lm can also hepl in
**argumentative and alternative communication (AAC)**.

> N-gram language model is a probabilist model that can estimate 
the **probability** of a word **given** the **n-1** previous word, 
and thereaby also assing probabilites to entire sequences.

## N-Grams
> P(w | h), is the probability of a word *w* given some history 
*h*. Suposse the history h is "Eu gosto de" and we want to know the
probability taht the next word is "laranja".

>> P(laranja | Eu gosto de)

> One way to estimative this probability is count all time we see
in corpus the history *h*, and count all time we see the history 
*h* and the next word is *laranja*.

>> P(laranja | Eu gosto de) = C(Eu gosto de laranja)/C(Eu gosto de)

> OBS: "Apesar de termos uma web cheia de repertório para 
treinamento, mesmo assim não temos probabilidades muito exatas  nos 
cálculos das sentenças, porque a linguagem é "CRIATIVA".
> -> New sentences are inveted all the time, and we can't expect to 
get accurate counts for such large objects as entire senteces.


P(Wn|W1:n-1) -> The probability the tokens (Word n) is the next 
after W1:n-1 tokens (sequence the Word 1, ..., Word n-1)

### The Markov Assumption

> This ideia, said if we have a history (one long sentence) and we 
need estimative the probability the next word given string *k*.
The correct form for calculs this is mencioned above, but markov 
said we can **aproximative** the probability just calculed one last 
short words the sequence history before string *k*. 

>> For example, P(Wn|W1:n-1) ~ P(Wn|Wn-1) (for bigram model)

> So ***Markov*** models are the class of probabilistic models that
assume we can predict the probability of some future unit without 
looking too far into the past. We can generalize the bigram (which 
looks one word into the past) to the trigram (which looks two words 
into the past) and thus to the n-gram (which looks n−1 words into 
the past).

### How to estimative probability

> Maximum Likelihood Estimation (MLE), we get the MLE estiamtive for
the parameter of an n-gram model by getting counts from a corpus, and
normalizing the count so that they lie between 0 and 1.

### Dealing with scale in large n-gram models

>


°Evaluating Language Models: Training and Test Sets
-Extrinsic Evaluation- :->
-Intrinsic Evaluation- :-> 

For evaluate any machine learning model is necessary three distinct datasets:
---> training set, development set and the test set;
- The traning set: is the data we use to learn the parameters of our model; for
simple n-gram language models it’s the corpus from which we get the counts that
we normalize into the probabilities of the n-gram language model.

- The test set: The test set is a different, held-out set of data, not 
overlapping with the training set, that we use to evaluate the model. We need a separate test set to give us an unbiased estimate of how well the model we
trained can generalize when we apply it to some new unknown dataset. A machine 
learning model that perfectly captured the training data, but performed terribly
on any other data, wouldn’t be much use when it comes time to apply it to any
new data or problem! We thus measure the quality of an n-gram model by its
performance on this unseen test set or test corpus.

- The development set (devset): 

°Evaluating Language Models: Perplexity
The perplexity (PP or PPL) of a LM on a set is teh inverse probability of the
test set, normalized by the number of words (tokens). 
*OBS: Search one definition in portuguese about perplexity in language models
for the fixing;*

So, if the higher is the probability of the word sequence, the lower the perple-
xity... Thus the lower perplexity of a model on the data, the better the model.
-> For this, minimixing perplexity is equivalent to maximizing the test set
probability according to the language model;

°Perplexity as Weighted Average Branching Factor
-> The branching factor of a language is the number of possible next words that
can follow any word.

°Generalizing vs . overfitting the training set "?"

° Smoothing, Interpolation, and Backoff
In this moment, the discussion is about the possibility of the probability is
zero and in the perplexity (function inverse of probability) it is a problem, because then we are estimate the perplexite, we cant, cant divide by zero. For this, have any algorithms for smoothing...
Laplace (add-one) smoothing, add-k, n-gram interpolation, and stupid
backoff.
