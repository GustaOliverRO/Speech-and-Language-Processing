# Logistic Regression and Text Classification

> The algorithm for classification is logistic regression, is equally
important. This algorithm have a close relationship with neural 
netwoks (neural networks can be viewed as a series of logistc
regression classifiers stacked on top of each other).


## Machine Learning and Classification

> Classification is to take a single input (we call each input an
**observation**), extract some useful features (characteries) or 
properties of the input, and thereby **classify** the observation
into one of a set of discrete classes.

>> Input x, and say that the output comes from a fixe set of output
classes Y = {y1,y2,...,yM}. Our goal is to return a predicted class 
from Y. Sometimes you'll the output classes referred to as set C 
instead of Y. For sentient analystic, the input x might be a review, 
or some  other text. And the output set Y might be the set:
- {positive, negative} or {0,1}

>> For language id, the input might be a text we need know what 
language it was written in, and the output set Y is the set of
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
- **test**: Given a test example x we compute the probability 
P(y = yi|x) for eachoutput class yi. Then, given this vector of 
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
weight wi features represent how important that input feature is to 
the classification decision, and can be positive (providing evidence 
that the instance being classified belongs in the positive class) or 
negative (providing evidence that the instance being classified 
belongs in the negative class).
The **bias term**, also called the **intercept**, is another real 
number that's added to the weigthed inputs.

- z = (sum i=1 até n de ((wi)(xi))) + b

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
of shape [m × f ], as follows:

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










# Resumo

> Logistic Regression and Text Classification, gira em torno da 
**classificação de textos usando regressão logística** (logistic 
regression).

- Text->Features->ModeloMatemático->Prob->Decison->Erro->Aprendizado
->Avaliação->Interpretaçõ->Regularização

## Machine learning and classification

> **Classification (Classificação)**, siginifica receber uma entrada 
e escolher uma categoria para ela. Cada input é uma *observation* 
(observação), represetado por *x* e há um conjunto de classes 
possíveis **Y** = {y1,y2,...,ym}, sendo o objetivo produzir
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
dele -> positivo. O problema é que regras manuais rapidadente ficam 
inviáveis por causa do seu aumento de complexidade. Há uma dificuldade 
em escrever regras para negação, sarcasmo, ironia, contexto, gírias...
- I love this movie -> postivo.
- I don't love this movie -> provavelmente negativo.

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
peso positivo significa que aquela feature favorece a classe 
positiva, enquanto o oposto serve para pesos negativos. Portanto,
uma feature pode ter peso positivo ou negativo, indicando evidência a 
favor ou contra uma determinada classe.

> **Combinação Linear** *z = (sum de i de 1 até n de (wixi)) + b* ou 
*z = w.x +b*, onde esse **z** representa uma forma de 
**pontuação de evidência**.
>> Exemplo: w = [2,-3], x = [4,1] e b = 0.5;
Então z = 2*4 + (-3)*1 + 0.5 = 5.5, o modelo produziu um valor para 
z, mas não é **uma probabilidade**, pois prob precisam estar entre 
0 a 1. z pode assumir valores infinitos + e -.

> **Sigmoid**, é uma função que recebe qualquer valor real e 
transforma-o em um intervalo de probabilidade. Valores muitos
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
- logit = log das odds, sigitica que o valor z, antes da sigmoid,
pode ser interpretado como evidência em escala de log-odds.

> **y^ - y-hat**, representa a previsão do modelo, no caso biário,
y^ = P(y=1|x) então:
- y  = resposta verdadeira
- y^ = previsão/probabilidade do modelo
>> Exemplo y = 1, mas y^ = 0.83, passa a informação de que o modelo
acretida em 83% de probabilidade que a classe seja 1.

## Classification with Logistic Regression
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

> **Escalonamento das Features**, neste caso é para tomar cuidado na
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
mais de uma observação, há uma forma otimizada fazendo álgebra 
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
1. Uma **loss function** para medir o erro;
2. Um algoritmo para minimizar o erro;

## The cross-entropy loss function

> Uma função de perca precisa distinguir bem os casos em que y^ pode 
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
probabilidade das resposta verdadeiras ser máxima, isto é, 
maximum likelihood estimation - estimação por máxima
verossimilhança.
- max P(y|x)
- max log P(y|x)
- min - log P(y|x) -> negative log-likelihood, cross-entropy loss
- **Ver exemplos**

## Gradiente Descent

> De forma geral o gradiente de uma função aponta para a direção de 
maior aumento da mesma, como queremos diminuir, iremos buscar a
direção oposta. Por isso a fórmula: θt+1 = θt - η∇L
- θ = parâmetros;
- ∇L = gradiente;
- η = learning rate (taxa de aprendizado)

> **Gradient**, se há vários parâmetros θ = [w1,w2,...,wn,b], o
gradiente será ∇L (vetor coluna) = **derivada da função loss em** 
**relação a cada um dos parâmetros presentes em θ**. Isso passa a
ideia matemática que "se eu alterar um pouquinho este parâmetro, 
quanto a loss muda?", uma dessa medida é a partial derivate.

> **Learning rate**, é a taxa de aprendizado, ela determina o quão 
rápido iremos na direção o posta do gradiente. Será um 
hyperparameter, e será escolhido pelo projetista do algoritmo.

> **Gradiente de Regressão Lógistica**, é uma das fórmulas mais 
importantes. ∂Lce​/∂wj = ​(y^ ​− y)xj = -(y - y^)xj, para da um dos
weigths, enquanto para o **bias** ∂Lce​/∂b = y^- y
- A interpretação vem *erro x feature* e passa a ideia de 'quanto
o modelo erro' x ' quanto aquela feature presente.
>> Exemplo
- x [3,2]
- y = 1
- w1 = w2 = b = 0
- η = 0.1
- w.x + b = 0 e η = 0.1 -> σ(0) = 0.5, logo y^ = 0.5;
- erro -> y^ - y = 0.5 - 1 = -0.5
- ∂Lce​/∂w1 = ​(-0.5)x1 = (-0.5)3 = -1.5
- ∂Lce​/∂w2 = ​(-0.5)x2 = (-0.5)2 = -1
- ∂Lce​/∂b = ​(-0.5)
- então ∇L=[-1.5,-1,-0.5]
- θ(new) = θ - η∇L, aplicando os valores
- w1 = 0.15; w2 = 0.1 e b = 0.05
>>> Ou seja, após ver um exemplo positivo (uma classificação correta),
o modelo aumenta os pesos das features presentes no exemplo.

> **Stochastic Gradient Descent**, é uma forma de calcular os pesos, 
a ideia central em vez de processar todo o dataset de uma única vez
(podendo ser "inviável"), pode escolher um observation aleatóriamente,
processá-lo (calculando assim seus pesos) e repetir o processo todo,
até ter processado todo o dataset
>> Exemplo
1. Escolhe um exemplo (observation)
2. Faz previsão (calcula o valor y^ com base no retorno da sigmoid)
3. Calcula erro (Usa a Lce para ver a loss)
4. Calcula o gradiente
5. Atualiza os pesos
6. Escolhe outro exemplo
7. Repete

> **Batch vs Mini-batch vs SGD**, são três processos "distintos" de
calcular o θ de todos os exemplos, alterando de forma geral somente
**m**, onde representa a quantidade de exemplos que serão processados
de uma única vez.

>> SGD, possui m = 1, processa uma observation por vez.

>> Mini-batch, possui m entre 512 a 1024.
- Aproveitam a vetorização e o paraleleismo do hardware;

>> Batch, irá atualizar de uma só vez o dataset por um todo.

## Multinomial Logistic Regression

A ideia central na MLR é quando temos mais de classes binária {0,1}
para classificar uma determinada entrada. Ou seja, dada uma observação
x e um conjunto de possíveis classes Y {0,1,...K}, como classificar 
com acertividade nesses casos. Nesse caso, usaremos oa multinominal
logistic regression, conhecida também como **softmax regression**, ou
maximum entropy/maxent classifier.

> **One-hot vector**, nesse caso atribui 1 a classe correta e 0 a todas
as outras. 
>> Ex:
- classes = [postive,negative,neutral]
- classificação para a entrada x -> negative;
- y = [0,1,0]

> **Softmax**, será usada para fazer a representação probabilística
para casos onde há mais do que duas classes. Essa função irá
transformar scores em uma distruibuição de probabilidade.

- Softmax(zi) = e^(zi)/ sum j de 1 até k de (e^(ezj))
- z = [0.6,1.1,-1.5,1.2,3.2,-1.1]
- softmax(z) -> [0.05,0.09,0.01,0.01,0.74,0.01] = 1

>> Exemplos
>>> Três classes
- positive   score = 2
- negative   score = 1
- neutral    score = 0
>>> z = [2,1,0]
>>> Aplicando softmax(z) = [0.67,0.24,0.09]

>>> A Distruibuição de probabilidade se dará por:
- positive → 67%
- negative → 24%
- neutral  → 9%

Fazer um exemplo para a Multinomial, sendo a entrada de um input x com 
mistura de linguas w,y,z e precise classificar qual é a lingua 
predominante.

> Binary vs Multinominal

>> Binary, temos uma único vetor de pesos w e y^ = σ(w.x + b)

>> Multinomial, muda pois terá um vetor de pesos para cada classe,
ou seja, Y = [1,2,...,K], teremos o w1,w2,...,wK, ou pode ser colocado
em uma matriz para representação **W**
>>> Então y^ = softmax(Wx+b)
>>>> Uma ideia interessante é enxergar cada linha wk da matriz **W**
como um "prototype" ?. Quanto mais a entrada se alinhas com 
determinado vetor, maior tende a ser o score daquela classe.
- classe positive -> vetor w1
- classe negative -> vetor w2
- classe neutral -> vetor w3

## Learning in Multinomial Logistic Regression
- A cross-entropy -> Lce (ŷ,y)= - (sum de k de 1 até K (yklog (ŷk)))
>> Como y é one-hot, somente uam posição vale 1, então se a classe 
correta for a c, ficamos com:
- Lce = -logŷc

>>> Exemplo
- classes {positive,negative,neutral};
- input x -> output negative
- y [0,1,0];
- modelo -> ŷ = [0.1,0.8,0.1]
- Loss será -> L = -log(0.8) = ~ 0.223
- Mas e se o ŷ = [0.45,0.05,0.50]
- A Loss seria -> L = -log(0.05) ~ 2.996

Conclui-se novamente que modelo confiante na resposta correta, loss
baixa, modelo confiante na resposta errada, loss alta.

## **Evaluation: Precision, Recall, F-measure**

A ideia aqui é avaliar se o modelo é bom 

> **Confusion Matriz** - matriz de confusão organiza as previsões
do sistema comparadas às respostas verdadeiras.
Ver imagem de uma 
- TP - true positive (predisse postivo e era positivo)
- FP - false positive (predisse positivo, mas era negativo)
- FN - false negative (predisse negativo, mas era positivo)
- TN - true negative (predisse negativo e era negativo)

> **Accuracy**, é um tipo de métrica, mas precisa ter 
cuidado com classes desbalanceadas;
- Accuracy = (TP+TN)/(TP+FP+TN+FN)

> **Precisison**, entre o que foi marcado pelo modelo como positivo,
quantos de fato eram ?
- Precision = TP/(TP+FP)

> **Recall**, de todos os postivios que realmente existiam, quantos
o modelo de fato encontrou ? 
- Recall = TP / (TP+FN)

> **F-measure**, é a combinação de P e R
- Fb = (b² +1)PR/ b²P+R, se b = 1, F = 2PR/P+R, sendo F a média
harmônica entre P e R.











