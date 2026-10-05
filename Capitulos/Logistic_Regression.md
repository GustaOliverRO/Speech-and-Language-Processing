# Logistic Regression and Text Classification

> The algorithm for classification is logistic regression, is equally
important. This algorithm have a close relationship with neural 
netwoks (neural networks can be viewed as a series of logistc
regression classifiers stacked on top of each other.


## Machine Learning and Classification

> Classification is to take a single input (we call eaxh input an
**observation**), extract some useful features (characteries) or 
properties of the input, and thereby **classify** the observation
into one of a set of discrete classes.

>> Input x, and say that the output comes from a fixe set of output
classes Y = {y1,y2,...,yM}. Our goal is to return a predicted class 
from Y. Sometimes you'll the output classes referred to as  set C 
instead of Y. For sentient analystic, the input x might be a review, 
or some  other text. And the output set Y might be the set:
  
- {positive, negative} or {0,1}

>> For language id, the input might be a text we need know what 
language it was written in, and the outpu set Y is the set of
langueges in the world

- Y = {Abkhaz, Ainu, Albanian,..., Zulu, Zuñi}
  
>> There are many ways to do classification. One method is to use 
rules handwrittenby humans. For example, we might have a rule like:

- If the word ‘‘love’’ appears in x, and it’s not preceded by the word 
‘‘don’t", classify as positive.
  
>> The most commom way yo do classification is to use 
**supervised machine learning**, is a paradigm in which, in addition
to the input and the set of output classes, we have a 
**labeled training set** and a **learning algorithm**
  
>> We can generally refer to a training set of m input/output pairs, 
where each input x is a text, in the case of text classification, and
each is hand-labeled with an associated class (the correct label).

- traning set: {(x^(1),y^(1)),(x^(2),y^(2)),...,(x^(m),y^(m))}. So for 
sentiment classification, a training set might be a set of sentences 
or other texts, each with their correct sentiment label.
  
> **Probabilist classifiers** like logistc regression are 
classifiers that in additon to giving an answer (the class this 
observation is in), also give the probability of the observation 
being in the class. Those components is four:
1. A **feature representation** of the input. For each input
observation x^(i), this will be a vector of features [x1,x2,...,xn].
2. A classifivation function that computes the estimated class, by 
computing the probability. **Sigmoid** ad **softmax**.
3. **Objective function** that we want to optimize for learning, 
usually involving minimizing a loss function, correspoding to a error
on training examples.
4. **Stochastic gradient descent** algorithm.

>> Logistic regression or any probabilist machine learning 
classifier, has two phases
- **training**: We train the system (in the case of logistic 
regression that means training the weights w and b, introduced below) 
using stochastic gradient descent and the cross-entropy loss.
- **test**: Given a test example x we compute the probability P(y = 
yi|x) for eachoutput class yi. Then, given this vector of 
probabilities, we return the higher probability label y = 1 or y = 0.

>>> Logistc regression can be used to classify an onservation into one
of two classes(like 'positives sentiment' and 'negative sentiment'),
or into one of many classes. Because the mathematics for the two-class 
case is simpler, we’ll first describe this special case of logistic 
regression in the next few sections, beginning with the sigmoid 
function, and then turn to multinomial logistic regression for more 
than two classes and the use of the softmax function.

## The sigmoid function

> Firt, consider a single input observation x, which we will represent
by a vector of features [x1,x2,...,xn]. The classifier the output y
can be 1 (meaning the observation is a member of the class) or 0 (not 
a member os the class)(positive sentiment vs negative sentiment). 
Logistic regression solves this taks by learning, from a training set,
a vector of **weigths** and a **bias term**. Each **weigth** wi is a
a real number, and associated with one of the iput features xi. The 
weight wi features represent how importatn that input feature is to 
the classification decision, and can be positive (providing evidence 
that the instance being classified belongs in the positive class) or 
negative (providing evidence that the instance being classified 
belongs in the negative class).
The **bias term**, also called the **intercept**, is another real 
number that's added to the weigthed inputs.

- z = (sum i=1 até n de ((wi)(xi)) + b

- z = **w**.**x** + b

>> But is necessary force z make a legal probability, in equation 
above z ranges from -infinit to +infinit. To create a probability,
we'll passe z in the **sigmoid** function, σ(z). This function is
called too a **logistic function**.

>> It's maps the range of z into the range (0,1), which is just what 
we want for a probability.

>> The sigmoid function has the property 1 - σ(x) = σ(-x)

>>  For binary classification it will be convenient to refer to the 
output ofthe sigmoid function σ(w·x+b) which is computing P(y = 1), as 
ˆy. We pronouncey hat this symbol as y hat. We thus use ˆy to mean 
“the probability of the input observayˆ tion having the positive 
class”. 

- σ(z) = 1 / (1 + e^(-z)) = 1 / (1 + exp(-z))

## Classification with Logistic Regression

> The sigmoid function from the prior section thus gives us a way to 
take an instaces x and compute the probability P(y = 1 | x). We say
yes if the probability above is more than 0.5, and no otherwiser.
- We call 0.5 the **decision boundary**

### Sentiment Classification

> Take a text, and this is a input. We'll represent each input
observation by the 6 features (x1, ..., x6). Let's assume for the 
moment that we've 6 weigthm corresponding a any features, while
b = 0.1. The weigth w1, indicates how important the feature x1 is to
a positive sentiment decision, if the weigth is bigger more important
is that features, if the weigth is smaller, minus importat is that
feature for a positive sentiment decison.

### Classification tasks and features

> ????

### Processing many examples at once

> In this case, we don't have classification just one input 
observation, we have classification one vector the input observation, 
we call **x^(i)**, onde 1 <= i <= m.
- First, we’ll pack all the input feature vectors for each input x 
into a single input matrix X, where each row i is a row vector 
consisting of the feature vector for input example x^(i). Assuming 
each example has f features and weights, X will therefore be a matrix 
of shape [m × f ].
- First, we’ll pack all the input feature vectors for each input x 
into a single input matrix X, where each row i is a row vector 
consisting of the feature vector for input example x^(i). Assuming 
each example has f features and weights, X will therefore be a matrix 
of shape [m× f ], as follows:

- **yˆ = σ(X w + b)**

- Why this equation above is diferent **σ(w · x + b)**

## Learning in Logistic Regression

>?
Ensinar com melhor exatidão o vetor de pesoas w e o escalar b,
alcançar um valor dos mesmo que maximize as estimativas para uma 
classificação de uma determinada observação


## The Cross-Entropy Loss Function

> 


## Gradient Descent










# Resumo Mais didático de tudo 

> Logistic Regression and Text Classification, gira em torno da 
**classificação de textos usando regressão logística** (logistic 
regression).

- Text->Features->ModeloMatemático->Prob->Decison->Erro->Aprendizado
->Avaliação->Interpretaçõ->Regularização

## Machine learning and classification

> **Classification (Classificação)**, siginifica receber uma entrada 
e escolher uma categoria para ela. Cada input é uma 
*observation* (observação), represetado por *x* e há um conjunto de
classes possíveis **Y** = {y1,y2,...,ym}, sendo o objetivo produzir
uma classe y pertencente a Y.
- Ex: em análise de sentimento: Y = {positive,negative} or {0,1}
- Input -> "This movie was fantastic!"
- CLASSIFIER
- Output -> postive

> **Classificação em NLP**, no processamento de linguagem natural
(NLP - Natural Language Processing), existem vários possivéis 
problemas de classificação.
>> Sentiment analytic - análise de sentimento
	"This movie was amazing!" -> positive

>> Spam detection - detecção de spam

>> Languagem identification - identificação de idioma

>> Authorship attribution - atribuição de autoria

> **Regras Manuais**, uma maneira de fazer classificação seria 
escrever regras: Se aparecer "love" e não aparecer "dont't" antes 
dele -> positivo.
- I love this movie -> postivo.
- I don't love this movie -> provavelmente negativo.
O problema é que regras manuais rapidadente ficam inviáveis por 
causa do seu aumento de complexidade. Há uma dificuldade em escrever
regras para negação, sarcasmo, ironia, contexto, gírias...

> **Supervised machine learning - aprendizado supervisionado**, o
início do machine learning. Há um conjunto de treinamento:
- {(x¹,y¹),(x²,y²),...,(x^m,y^m)}
- Cada par é composto por uma entrada x e uma resposta correta y.

>> Exemplo:
Texto x - Label y
Amazing movie - positive
Terrible movie - negative
...

>>> O label é a resposta correta fornecida durante o treinamento, 
pois existe um "supervisor": o conjunto de dados rotulado, sendo 
esse o training set, sendo o conjunto de pares em que cada input
(observação) está associado a um output (classe correta - label).

> O modelo não simplismente memoriza uma classificação, mas ele 
aprende com *pesos associados às features*. Um classificador 
probabilístico tem quato componente:
1. Feature representation
2. Clssification function
3. Objetive/loss functin
4. Optimization algotirhm

> **Parâmetros e treinamento**, a regressão logística possui 
principalmente: **w** (weights) e **b** (bias/viés), durante o 
treinamento, o modelo tenta descobrir bons valores para esses 
parâmetros. Sendo tudo feito em duas grande fase:
- Training (aprender **w** e **b**).
- Test (receber uma nova entrada e calcular suas possibilidades).

## The sigmoid Function
- O caso inicial estudado é **binary logistic regression** -
regressão logística binária. (classe 0 ou classe 1)
- Queremos descobrir: P(y=1 | x), "qual a probabilidade de y = 1, 
dado o texto" ?

> **Features**, suponha que uma resenha seja representada por:
x = [x1,x2,x3], onde:
- x1 = quantidade de palavras positivas;
- x2 = quantidade de palavras negativas;
- x3 = presença de "!";
>> Exemplo: "Great movie! Amazing!", temos x = [2,0,1], o computador
não trabalha diretamente com o significado abstrado da frase. Ele 
trabalha com uma **representação númerica**.

> **Weigths - Pesos**, cada feature possui um peso [w1,w2,...,wn], 
representa quanto aquela característica influência na decisão. Um
peso postivo significa que aquela feature favorece a classe 
positiva, enquanto o oposto serve para pesos negativos. Portanto,
uma feature pode ter peso postivo ou negativo, indicando evidência a 
favor ou contra uma determinada classe.

> **Combinação Linear** *z = (sum de i de 1 até n de (wixi)) + b* ou *z = w.x +b*, onde esse **z** representa uma forma de 
**pontuação de evidência**.
>> Exemplo: w = [2,-3], x = [4,1] e b = 0.5;
Então z = 2*4 + (-3)*1 + 0.5 = 5.5, o modelo produziu um valor para 
z, mas não é **uma probabilidade**, pois prob precisam estar entre 
0 a 1. z pode assumir valores infinitos + e -.

> **Sigmoid**, é uma função que recebe qualquer valor real e 
transforma o em um intervalo de probabilidade. Valores muitos
negativos viram probabilides próxima de 0, valor 0 vira 
probabilidade 0.5 e valores muito grande tende a ser probabilidades
próximas a 1.
- σ(z) = 1 / (1 + e^(-z))
- 0 < σ(z) < 1

> **Probabilidade das duas classes**, como só há duas possibilidades
a soma deve ser igual a 1, então pode se fazer cálculos simples com 
base em uma probabilidade para encontrar a outra.
- P(y = 1 | x) = σ(w . x + b) e P(y = 0 | x) = 1 - σ(w . x + b)
- P(y = 1 | x ) + P(y = 0 | x) = 1

> **Logit**, z = w . x + b é *logit*, sendo a função inversa da 
sigmoid é logit(p) =  ln(p/1-p), onde p/1-p é chamado de **odds**.
- logit = log dad odds, sigitica que o valor z, antes da sigmoid,
pode ser interpretado como evidência em esacala de log-odds.

> **y^ - y-hat**, representa a previsão do modelo, no caso biário,
y^ = P(y=1|x) então:
- y  = resposta verdadeira
- y^ = previsão/probabilidade do modelo
>> Exemplo y = 1, mas y^ = 0.83, passa a informação de que o modelo
acretida em 83% de probabilidade que a classe seja 1.

## **Classification with Logistic Regression**
- Agora há uma probabilidade, mas ainda é necessário tomar uma
decisão.

> **Decision boundary - fronteira de decisão**, o livro escolhe como
fronteira de decisão 0.5, então decision(x) = {1 (P(y=1|x) > 0.5) ou
0 (c.c)}. Note que probabilidade e desisão não são a mesma coisa, o
modelo produz uma probabilidade e o limiar transforma essa
probabilidade em uma desição discreta.
>> Exemplo:
- y^ = 0.91 -> classe 1
- y^ = 0.51 -> classe 1
- y^ = 0.49 -> classe 0
- Seja x = [3,2,1,3,0,4.19]
- Seja w = [2.5,-5,1.2,0.5,2,0.7]
- Seja b =0.1
- z = w . x + b = 0.833
- y^ = σ(0.833) ~ 0.70
- P(+ | x) = 0.70 e P(- | x) = 0.30

> **Esclonamento das Features**, neste caso é para tomar cuidado na
discrepância da quantidade de uma feature para outra, sendo por 
exemplo x1 = 2 e x2 = 500000, pode haver essa dominância. Por isso
há uma padronização - *standardization*, chamada de z-score, ou 
normalização - *normalization*
>> standartization = x'i = (xi - mi)/deltai
- mi = média;
- deltai = desvio padrão

>> normalization = x'i = (xi - min(xi))/ max(xi)-min(xi)

>>> Isso coloca os valores aproximadamente ente 0 e 1.

> **Processando muitos exemplos**, isso se dá quando for necessário
mais de uma onservação, há uma forma otimizada fazendo álgebra 
matricial.
- Deseja processar uma sequencia de m observação x¹,x²,...,x^m

>> Construimos um matriz onde cada linha é representa um exemplo.
>>> Se temos m exemplos e f features então ***X***∈R^(m x f)
- o cálculo vira: y^ = σ(***X***.w + b), a sigmoid é aplicada a cada
um dos elementos.

## Learning in Logistic Regression

> Como encontrar os valores **w** e *b* ?
> Queremos a maior aproximação possível de y^ ~ y. Para isso
precisamos de duas coisas:
1. Uma **loss function** para medior o erro;
2. Um algoritmo para minimizar o erro;

## The cross-entropy loss function

> Uma funça de perca precisa distinguir bem os casos em que y^ pode 
afetar de maneira grotesca, decidir de forma confiante um erro. 

> **Cross-entropy**, é apresentado o cross-entropy loss - perda de
entropia cruzada. Lce (y^,y)=-[ylogy^ + (1-y)log(1-y^)].
>> Para casos onde y = 1, sustituindo temos L = -logy^
>>> **Ver o que valores de y^ causam.**

>> Para caso onde y=0, temos L = -log(1-y^)
>>> **Ver o que valores de y^causa.**

>> O log é usado porque **penaliza fortemente previsões erradas**
**e confiantes**. Ou seja, atribuir probabilidade praticamente zero
à resposta correta é extremametne penalizado.
>>> **Ver exemplos de aplicação para exemplo**

> **Maximum likelihood**, queremos escolher w e b que façam a 
probabilidade das resposta vrdadeiras ser máxima, isto é, 
maximum likelihood estiamtion - estimação por máxima
verossimilhança.
- max P(y|x)
- max log P(y|x)
- min - log P(y|x) -> negative log-likelihood, cross-entropy loss
- **Ver exemplos**

## Gradiente Descent

> De forma geral o gradient de uma função aponta para a direção de 
maior aumento da mesma, como queremos diminuir, iremos buscar a
direção oposta. Por isso a formula:
- Theta = parâmetros
- ... = gradiente;
- ... = learning rate (taxa de aprendizado)

> **Gradient**, se há vários parâmetros theta = [w1,w2,...,wn,b], o
gradiente será ... (vetor coluna) = derivada da função loss em 
relação a cada um dos parâmetros presentes em theta. Isso passa a
ideia matemática que "se eu alterar um pouquinho este parâmetro, 
quanto a loss muda?", uma dessa medida é a partial derivate.

> **Learning rate**, é a taxa de aprendizado, ela determina o quão 
rápido iremos na direção o posta do gradiente. Será um 
hyperparameter, e será escolhido pelo projetista do algoritmo.

> **Gradiente de Regressão Lógistica**, 































