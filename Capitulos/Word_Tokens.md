# Words and Tokens

## Words

-> I do uh main- mainly bunisses data processing

Utterance ? ->

Disfluencies ? ->


Fillers or Filled Pauses, is a words type **uh** or **um**;

-> They picnicked by the pool, then lay back on the grass and looked at the 
stars.  

> We call the set od **unique** words in a corpus the word ***types***. In
the sentence above has 14 word types;

>**Unknown words**, this is about no matter how big or vocabulary, we will
never have a vocabulary that capturs all the possible words that migth
occur. In sintaxe, uknown words is **words it has never seen before**, and
this is a huge problem for machine learning models. 

## Morphemes

> Is a minimal meaning-bearing unit in a language (unidade mínima que
expressa um sentido na linguagem ?);

> We generally distinguish two broad classes of morphemes: **roots** - the
central morphemeof the word, supplying the main meaning - and **affixs** -
adding "extra" meanings of various kinds. 
Ex: Pedregulho, root - Pedr (Pedra), affixes - egulho;

> Affixes themselves two classes, or more correctly two poles. 
>> Inflectional Morphemes, are gramtmatical morphemes that tend to play a 
syntatic role, make one word to plural or pst tense on verbs. (-s,-es,-ed);
>> Derivational Morphemes, are more idiosyncratic in their applicantion and 
meaning. Usally if apply in one word, this word is gonna a *different 
grammatical class*. care; careful; carefully;

## Characters in Computer

> ASCII -> Unicode -> UTF-8

## Subword Tokenization: Byte-Pair Encoding

**Tokenizantion**, the first stage of natural language processing, is the
process of segmenting the running input text into **tokens**. 

> Tokenization algorithms that include smaller tokens for morphemes and 
letter also eliminate the problem of unknown words. To nknown word problem, 
modern tokenizers automatically induce sets of tokens that include tokens 
smaller than words, called **subwords**. Subwords can be arbitrary 
substrings, or they can be meaning-bearing units like the morphemes -est or 
-er.

> Two tokenization algorithms are widely used in modern language models: 
byte- pair encoding (BPE) and unigram language modeling (ULM). The BPE has 
two parts: a **training phase** and the **enconder** phase. In general, in 
the token phase the tokenizer takes a raw training corpus (usually roughly 
pre-separated into words, for example by whitespace) and induces a 
vocabulary, a set of tokens. The in the encoding phase the tokenizer takes 
a  raw test sentences and encodes it into the tokes inte vocabulary that 
were learneed in training. 


### BPE traning
> The *BPE* traning algorithm iteratively merges frequent neighboring 
tokens
to create longer and longer tokens. The algorithm begin with a vocabulary 
that is just the set of all individual characters.  Is similar the 
Hullfman 
Algorithm, because the output the firt input in incremented and used for
input with the new executing the algorithm;
>> Example:
>> Parte 1
>> Input: set_ new_ new_ renew_ reset_renew
>> corpus: 2 _new
					 2 _renew
					 1 set
					 1 _reset
>> vocabulary: _, e,n,r,s,t,w
>> most frequent is **n** and **e**, merge these symbols, add **ne** to 
vocabulary and count again.  

>> Parte 2
>> corpus: 2 _new
					 2 _renew
					 1 set
					 1 _reset
>> vocabulary: _, e,n,r,s,t,w,ne
>> most frequent now is **ne** and **w**, so merge these symbols, add 
**new*** to vocabulary and count again. 

>> Parte 2
>> corpus: 2 _new
					 2 _renew
					 1 set
					 1 _reset
>> vocabulary: _, e,n,r,s,t,w,ne,new
>> most frequent now is **_** and **r**, merge these and add to vocabulary.
>> After total proccess to algorithm the result of vocabulary is:
>> vocabulary: _ ,e,n,r,s,t,w,ne,new, _r, _re, _new, _renew,se,set

### BPE encoder

> Once we’ve learned our vocabulary, the BPE encoder is used to tokenize a 
test sentence. The encoder just runs on the test data the merges we have 
learned from the training data. It runs them in the order we learned them. 
he frequencies in the test data don’t play a role, just the frequencies in 
the training data. So first we segment each test sentence word into 
characters. Then we apply the first rule: replace every instance of n e in 
the test corpus with ne, and then the second rule: replace every instance 
of ne w in the test corpus with new, and so on. 

### BPE in practice

## Corpora

> Is one expression in latim and represent plural of Corpus. Corpus, "é um 
grande conjunto estrtuturado de textos escritos ou falados, reunidos de
forma criteriosa para servir de base em pesquisas sobre uma língua. 
Portanto, corpora resere-se a dois ou mais desses conjuntos de dados 
linguísticos".

## Regular Expression

> Is an algebraic notation for characterizing a set of strings. 
Practically, we can use a **regex** to search for a sting in a text and to 
specify how to change the string, both of which are key to ttokenization.  

> Search about 're.search', function in Python;


>> Stoped in **2.9 Minimum edit Distance**;












