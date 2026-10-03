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

> **Log Probabilities**, language model probabilities are always stored 
and computed in log space as *log probabilities*. This is because 
probabilities are (by definition) log probabilities less than or equal 
to 1, and so the more probabilities we multiply together, the smaller 
the product becomes. Multiplying enough n-grams together would result in 
numerical underflow. Adding in log space is equivalent to multiplying in 
linear space, so we combine log probabilities by adding them. 

## Evaluating Language Models: Training and Test Sets

> Extrinsic Evaluation, is the only way to know if a particular 
improvement in the language model (or any component) is really going to 
help the taks at hand.

> Intrinsic Evaluation, is a metric one that measures the quality of a 
model independent of any application. 

> For evaluate any machine learning model is necessary three distinct 
datasets:

>> The traning set: is the data we use to learn the parameters of our 
model; for simple n-gram language models it’s the corpus from which we 
get the counts that we normalize into the probabilities of the n-gram 
language model.

>> The test set: is a different, held-out set of data, not  overlapping 
with the training set, that we use to evaluate the model. We need a 
separate test set to give us an unbiased estimate of how well the model 
we trained can generalize when we apply it to some new unknown dataset. A 
machine learning model that perfectly captured the training data, but 
performed terribly on any other data, wouldn’t be much use when it comes 
time to apply it to any new data or problem! We thus measure the quality 
of an n-gram model by it's performance on this unseen test set or test 
corpus. In this dataset, we want to rin our model on the test set once,
or a very few number of times, once we are sure our the model is ready.

>> The development set (devset): we do all our testing on this dataset
until the very end, and then we teste on the teste set once to see how 
goos our model is.

>>> Observation, if our test sentence is part of the training corpus, we 
will mistakenly assign it an artifically high probability when is occurs
in the teste set. We call this situation **training on the test set** or
also **data contamination**. 

## Evaluating Language Models: Perplexity

> The perplexity (PP or PPL), is a function of probability used for 
evaluating large language models as well as n-gram model. The **PP** of a 
LM on a test set is the inverse probability of the test set, normalized 
by the number of words (tokens). 
- OBS: Search one definition in portuguese about perplexity in language 
models for the fixing;

perplexity(W) = P(w1w2...wN)^(-1/N)

> A language model is good if it predicts the words present in the test
et with high probability. **Perplecity** is the inverse probability of 
the test set, normalized by the number of words (tokens ?). In pratice,
we use log probs which is exponentiated token level netative 
log-likelihood. So, intuitively perplexity is the number of option you
have for the next predicted word, **lower the options better the model**.

>> So, if the higher is the probability of the word sequence, the lower 
the perplexity. Thus the lower perplexity of a model on the data, the 
better the model. For this, minimixing perplexity is equivalent to 
maximizing the test set probability according to the language model;

> Perplexity can be used to compare different language models. Is good, 
the LM use the same training data set and is necessary carreful about
data contamination, or else the perplexity will be artificially low.

### Perplexity as Weighted Average Branching Factor

> The branching factor of a language is the number of possible next 
words that can follow any word.
> Update this part...

## Sampling sentences from a language model
- -> ?


## Generalizing vs . overfitting the training set

- -> ?

## Smoothing, Interpolation, and Backoff

> In this moment, the discussion is about the possibility of the 
probability is zero and in the perplexity (function inverse of 
probability) it is a problem, because then we are estimate the 
perplexite, we can't (can't divide by zero). For this, have any 
algorithms for smoothing (?).

Laplace (add-one) smoothing, add-k, n-gram interpolation, and stupid
backoff.


## Advanced:Perpexity's Relation to Entropy

> **Entropy** ia a measure of information.



#### Resumo

> Perplexidade é a média geométrica do inverso das probabilidades que o 
modelo atribuiu aos tokens corretos.

>> Exemplo

>> "Eu gosto de Pizza"
>> P(eu)=0.5
>> P(gosto|eu)=0.4
>> P(de|eu gosto)=0.5
>> P(pizza∣eu gosto de)=0.8
>> P(W) = 0.5 * 0.4 * 0.5 * 0.8
>> P(W) = 0.08

>> PP(W) = 0.08^(-1/4) ~ 1.88
>> O modelo se comporta como se tivesse, em média, cerca de 1,88 
possibilidades igualmente prováveis para o próximo token.

>> Perplexidade não é simplesmente o número de palavras possíveis. É o 
número efetivo de possibilidades, levando em consideração suas 
probabilidades. (Com base no subtópico de Branching Factor)

>> Na fórmula de Perplexidade vale a pena ressaltar que a raiz de 
N, sendo N o número de tokens, está ali para normalizar e trazer 
um resultado mais palpável e de melhor comparação com corpus de 
tamanhos distintos, ou seja, que seja possível analisar o dataset
A com 1000 palavra e o dataset B com 10⁷ palavras;

> Entropia mede a incerteza de uma váriavel aleatória. E no pdf, 
é apresentada a Fórmula H(X). Onde o log2, siginifica que os dados
são mensuarados em bits.

- Exemplo: Para moedas justas, 0.5 de probabilidade para cara ou
coroa, se aplicarmos esses dados em H(X), teremos como resultado **1**, 1 
bit. Isso nos da que precisamos de exatamente 1 bit para representar o 
resultado. 

- A entropia está profudnametne relacionada à quantidade mínima de 
informação necessária para representar resultados de uma distribuição 
probabilística.

- Mais incerteza -> maior entropia

- Mais previsivilidade -> menor entropia

> Perplexidade: Perplexidade é uma métrica usada para avaliar modelos de 
linguagem. Ela corresponde à probabilidade inversa da sequência de teste, 
normalizada pelo número de tokens. Pode ser interpretada como um fator de 
ramificação médio ponderado e, usando log₂, é igual a 2^H, onde H é a 
cross-entropy por token. Quanto menor a perplexidade, melhor o  modelo 
prediz os dados de teste.

> Entropia: Entropia mede a incerteza média de uma distribuição de 
probabilidade, ou equivalentemente a quantidade média de informação 
necessária para representar seus eventos.

> Cross-Entropy: Cross-entropy mede o custo médio de representar dados 
provenientes de uma distribuição verdadeira p usando um modelo m. Ela é 
dada por - [sum p(x)log m(x)], e é mínima quando o modelo  coincide com a 
distribuição verdadeira.

- Cross-Entropy -> Perplexidade

- PP = 2^H

