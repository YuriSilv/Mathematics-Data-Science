# Mathematics-Data-Science

- [Calculus](#1.0-calculus)
    - [Limits](#1.1-limits)
    - [Limits Rules](#1.2-limits-rules)
    - [Limits Infinity](#1.3-limits-infinity)
    - [Derivatives](#1.4-derivatives)
    - [Derivatives Example](#1.4.1-derivatives-example)
    - [Derivatives Python](#1.4.2-derivatives-python)
    - [Derivatives Rules](#1.5-derivatives-rules)
    - [Min-Max](#1.6-derivatives-min-max)
    - [Newthon's Method](#1.7-derivatives-newtons-method)
    - [Integrals](#1.8-Integrals)
    - [Cálculo com Vetores]({#1.9-calculo-com-vetores})

- [Statics and Probability](#2.0-statics)
    - 2.1 Descritive

- [Linear Algebra](#3.0-linear-algebra)
    - 1.1


## 1.0 Calculus {#1.0-calculus}
Motivação: permite entender fenômenos importantes em um ambiente, como a velocidade instântanea de um objeto.
Aplicado a ML e DL, podemos gerar "gradientes", que são uma forma de atingir uma otmização de uma equação. Ou seja, uma forma de aprender. 
![Exemplo Gradiente](https://poissonisfish.files.wordpress.com/2020/11/non-convex-optimization-we-utilize-stochastic-gradient-descent-to-find-a-local-optimum.jpg)

### 1.1 Limits {#1.1-limits}
Definição Intuitiva: Em um plano contínuo representando uma função que pertence aos números reais, ou seja, pode abranger infinitos valores entre dois pontos específicos, o limite de uma função é dado como o resultado - ou talvez o comportamento - da função quando o valor de x se aproxima infinitamente de um ponto determinado. No exemplo abaixo, o limite de f(x) quando x tende a "a" é igual L
\[ \lim_{x \to a} f(x) = L \]


Logo, devido a sua capacidade, os limites são úteis para enterdemos a tendência de uma função, por mais bizarra que ele possa ser. Por exemplo:
![Exemplo de limite](imgs/limites.png)

#### 1.2 Limits Rules {#1.2-limits-rules}
-Distributiva: o limite pode ser distriuído na soma, subtração, multiplicação ou divisão de duas funções ou mais funções
-Comutatividade sobre constantes: a constante que multiplica uma função em um limite pode ser colocada antes ou depois a execução do limite. Em essência, isso também é válido para a exponenciação e raízes.

Em resumo:
![limit rules](https://mathtuition88.files.wordpress.com/2022/05/image-13.png)

#### 1.3 Limits Infinity {#1.3-limits-infinity}
Na matemática, podem existir funções que tentam alcançar um valor, sempre se apróximando dele, mas nunca verdadeiramente o atingindo. 
Por exemplo, a função 1/x tende sempre a buscar o valor 0, mas nunca de fato o toca.
![Exemplo de limite](imgs/1sobrex.png)

Disso, temos que \[\lim_{{x \to \infty}} \frac{1}{x} = 0\]
Ou seja, quanto mais x cresce, mais próximo de 0 ele fica. Logo, ele tende ao infinito, que nunca será atingido, já que ele é infinito.

De outra forma, podem existir funções que tendem ao infinito, resultando uma resposta infinita, e funções que tendem ao infinito, mas a resposta simplesmente não existem, como lim x→∞​ sin(x). Nesse último caso, isso ocorre porque a função seno oscila entre 1 e -1, então mesmo que x cresça infinitamente, ela não vai converger.

Por fim, deve-se pontuar que existem infinitos negativos ou positivos, que devem ser usados conforme a função que se análisa. Além disso, certas operações com infinitos podem gerar números indeterminados (diferentes de não exister), por exemplo infinito/infinito.
OBS: As vezes, é possível fugir desses números indeterminados fazendo manipulações nas fórmulas.

### 1.4 Derivatives {#1.4-derivatives}
Imagine uma curva que represente algum fenômeno, como a velocidade não uniforme de um objeto. Podemos calcular a variação desse fenômeno definindo dois pontos e fazendo a divisão de sua diferença em seus eixos ((y2-y1)/(x2-x1)). Se aproximarmos o ponto mais distante (p2) do primeiro ponto (p1), a reta secante que antes tocava apenas dois pontos, tenderá a tocar somente um ponto.
![Derivatives](https://www.math.net/img/a/calculus/limit-definition-of-a-derivative-1.png)
Disso, podemos definir a derivada como o limite da aproximação da reta secante em um determinado ponto. Na prática a derivada nos retorna um vértice em um gráfico contínuo.
A derivada de \( f(x) \) em relação a \( x \), denotada por \( f'(x) \) ou \( \frac{df}{dx} \), é definida como:

\[ f'(x) = \lim_{{h \to 0}} \frac{f(x + h) - f(x)}{h} \]
"h" tender a 0 significa que a distância entre os pontos tende a 0.
No exemplo de um corpo em movimento, esse cálculo trará a velocidade instantânea.

Deve-se pontuar que nem todas funções podem ser derivadas. Alguns exemplos que não podem ser derivados (by chat gpt):
 - Descontinuidades: Uma função não deve ter descontinuidades abruptas para ser derivável. Descontinuidades podem ocorrer em pontos isolados ou ao longo de um intervalo.
 - Pontos angulosos ou cúspides: A presença de pontos angulosos ou cúspides na curva da função pode indicar a falta de derivabilidade nesses pontos. Cúspides são pontos onde as retas mudam a difereção
 - Assimetria extrema: Funções altamente assimétricas, especialmente aquelas com comportamento oscilante excessivo, podem apresentar dificuldades de derivabilidade em alguns pontos.
 - Divisão por zero: Se a função envolve uma divisão por zero em algum ponto, a derivada pode não existir nesse ponto.

#### 1.4.1 Derivatives Example {#1.4.1-derivatives-example}
![Derivatives with limites](https://useruploads.socratic.org/FtiQLgBqTGcPettrBV1n_limit%20definition1.png)
Fonte: https://socratic.org/questions/how-do-you-find-the-derivative-using-limits-of-f-x-3x-2

#### 1.4.2 Derivatives Python {#1.4.2-derivatives-python}
No python, para se calcular uma derivada, basta inputar um "h" muito próximo de 0 na fórmula do limite, que obteremos um valor aproximado satisfatório. Ou seja, não precisamos necessariamente descobrir qual é a função da derivada, apesar de que isso pode ajudar em alguma otmização.

#### 1.5 Derivatives Rules {#1.5-derivatives-rules}
As vezes as funções podem ser muito complicadas de serem resolvidos pela intuição de limite. Disso, foi percebido que existem regras que sempre se aplicam as derivadas, que podem servir de atalhos em suas resoluções. Essas regras são:

![Derivatives rules](https://www.onlinemathlearning.com/image-files/basic-derivative-rules.png)

Fonte: https://www.onlinemathlearning.com/derivative-rules.html

![Derivatives rules log example](https://www.onlinemathlearning.com/image-files/derivatives-logs.png)
Fonte:https://www.onlinemathlearning.com/derivative-ln.html

![Derivatives rules example](https://www.geneseo.edu/~baldwin/math221/fall2019/derivativerules.png)
Fonte:https://www.geneseo.edu/~baldwin/math221/fall2019/09-slash-18-basic-differentiation-rules.php

Não é necessário decorar essas regras, apenas saber que elas existem e podem ser úteis para simplicar uma função.

#### 1.5.1 Chain Rule {#1.5.1-chain-rule}

Algumas funções podem precisar serem decompostas para se aplicar as regras acima. Tais funções muitas vezes vem em formato de funções compostas, que apresentam uma regra especial.
Essa regra é conhecida como regra da cadeia, e permite transformar a função em multiplicações de derivadas, da composta sobre a interna. Exemplo:
![Chain rule](https://www.a-levelmathstutor.com/images/calculus/chain_rule_03M.jpg)

Fonte:https://www.a-levelmathstutor.com/chainrule.php

Essa regra é interessante pois ela é muito utilizada em redes neurais. Já que uma rede neural é composta por um conjunto de funções compostas. Ou seja, dado uma entrada x que pecorrer f'(x1), f'(x2), ..., f(xn), temos o resultado y.

#### 1.5.2 Derivatives LHopital {#1.5.2-derivatives-lhopital}
![lhopital](https://cdn1.byjus.com/wp-content/uploads/2020/02/l-hospital-formula.png)

#### 1.5.3 Implicit Derivatives {#1.5.3-implicit-derivatives}
Algumas funções vem em formato implicito, ou seja, o x e y estão do mesmo lado da igualdade.  Em outras palavras, você tem uma equação que relaciona duas ou mais variáveis, e pode não ser possível isolar uma variável em termos da outra explicitamente. Para calcular derivadas implícitas, deve-se trata uma variável como uma função da outra e, em seguida, diferencia a equação em relação à variável independente. Isso geralmente é feito usando a regra da cadeia. Exemplo: https://www.youtube.com/watch?v=GxI2-rZnfjs

#### 1.6 Derivatives Min-Max {#1.6-derivatives-min-max}
Imagine um gráfico de uma função. Esse gráfico pode ter um ponto mais baixo ou um ponto mais alto em uma determinada coordenada - podendo, é claro, haver mais de um ponto alto e baixo ao mesmo tempo-. Através de derivadas podemos encontrar o ponto mínimo ou máximo de dessa ou outra função, algo que é bastante útil nos algoritmos de machine learning.

Havendo mais de um max ou min, o menor mínimo/máximo é chamado de global mínimo/máximo, enquanto os outros menores são chamados de local mínimo/máximo - importante notar que algumas funções, como a seno, tem vários globais min/max -.

Para se encontrar esses min-max, alguns testes se aplicam durante a análise.
1º Teste:
Se f' muda de + para - (ou o contrário) em um ponto c, então f(c) é um mínimo local.
![First derivative teste](https://images.slideplayer.com/31/9732336/slides/slide_13.jpg)

2º Teste:
Se a derivada da derivada (f'') é maior que 0, então sua concavidade é voltada para cima - logo estamos tratandos de um mínimo-. Paralelamente, se f'' < 0, então temos uma concavidade para baixo e estamos lidados com um máximo.

Se f'' = 0, pode ser um mínimo, máximo ou nenhum dos dois -inconclusivo- .

Exemplo:
![Example min-max derivative](https://i.ytimg.com/vi/pvLj1s7SOtk/sddefault.jpg)

#### 1.7 Derivatives Newtons Method {#1.7-derivatives-newtons-method}
Um primeiro preludio dos algoritmos de otmização é o método de Newton's, que irá permiter fazer uma iteração sobre uma determinada função, a fim de encontrar qual o valor de f(x) quando ele é igual a 0, ou seja, quando x é 0.
![Newtons Method](https://andymath.com/wp-content/uploads/2019/08/newtons-method-notes.jpg)

Mais informações: https://www.youtube.com/watch?app=desktop&v=-5e2cULI3H8


#### 1.8 Integrals{#1.8-Integrals}
Essencialmente, integrais são o contrário das derivadas. Isso quer dizer que dado uma função já derivada, podemos voltar a sua versão original, fazendo o caminho inverso.
Por exemplo, para derivarmos x^2, temos 2x. Ou seja, a integral de 2x é x^2 + c. Note que existe um termo "c" que é acoplado juntamente com a função. As vezes esse termo pode ser omitido, mas a ideia geral é que ele existe pois algumas constantes, quando estão sendo somadas, desaparecem da derivada, pois sua derivada é 0. Isso ocorre em integrais *indefinidas*, que não tem um range predefinido (como indo de "a" até "b")

Falando sobre suas aplicações, elas são diversas, como estatísticas e probabilidades, cadeias de markov, área de uma função, etc.
O exemplo mais prático é a área sobre uma determinava curva de função. Podemos criar vários pontos imaginários ao longo da função que criam um range (x1-x), que traçados para baixo formam um retângulo. Se criarmos vários pontos e fazer um somátorio deles, teremos uma área apróximada da curva. Agora se criarmos infinitos intervalos de ponto(tender ao infinito), teremos a área exata daquela curva
![Area sobre a curva](https://i.ytimg.com/vi/FsC3do74UIo/maxresdefault.jpg)

#### 1.8.1 Teorema Fundamental {#1.8.1-teorema-fundamental}
O teorema fundamental 1 do Cálculo é uma forma de relacionar derivadas e integrais. Para tal:
![Teorema 1](https://media.nagwa.com/605194347359/en/thumbnail_l.jpeg)

Por sua vez, o segundo teorema, demostra um atalho para se resolver integrais. Em vez nos aproximarmos do infinito, podemos fazer uma subtração, o que economiza muito o processamento. Ele pode ser representado como:
![Teorema 2](https://miro.medium.com/v2/resize:fit:1400/1*xXK2CDtdItq79-iaeCfDJQ.png)


#### 1.8.2 Exemplos Integrais {#1.8.1-exemplos-integrais}
Exemplo 01 - Integral Indefinida Continua:
![Ex. 1](https://cdn1.byjus.com/wp-content/uploads/2018/11/maths/2016/06/03100536/Continuous-Integration.jpg)

Exemplo 02 - Integral Definida:
![Ex. 2](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQMHEmoCGgZAjsSm8KlU2Ta8AaO2YTzxQQXR0RzKRy9X0C-iCsLrrGJ2-IFt27QTnXng5k&usqp=CAU)

Exemplo 03: Usando substituição em U:
![Ex. 3](https://qph.cf2.quoracdn.net/main-qimg-fc04b72c15e3f841a5f29cba12d5af12-pjlq)

Exemplo 04: Aproximando do infinito (Nem sempre a área vai ser infinita):
![Ex. 4](https://www.dummies.com/wp-content/uploads/205597.image0.png)


#### 1.9 Calculo com vetores {#1.9-calculo-com-vetores}
Definição de vetores: uma medida quantitativa que tem direção e magnitude("força").
É comum funções existirem com múltiplos inputs de entrada, como vetores. Isso pode resultar em um escalar (número com 1 dimessão) ou um vetor.

#### 1.9.1 Derivadas parciais {#1.9.1-derivadas-parciais}
É possível derivar uma função com múltiplas variáveis utilizando-se das derivadas parciais.
Nela, se deriva cada variável separadamente, considerando as demais como constantes. Sua notação é um pouco diferente, como demonstrado abaixo, com as derivadas de x, y e z.
![Ex. derivada parcial](https://math.info/image/255/partial_derivatives_ex.gif)

Importante notar que as derivadas ainda mantém seu objetivo de origem, encontrar linhas tangentes. A diferença é que agora isso está sendo feito em um espaço n-dimensional.

#### 1.9.2 Gradientes {#1.9.2-gradientes}
Um gradiente é uma função multivariável que o output resulta em um escalar (se o resultado for um vetor, ele será um jacobian, que é útil para processamentos de matrizes). Sua vantagem é que eles podem ser utilizado em métodos de otmização de funções complexas.
Ele também pode ser visto como o vetor de derivadas parciais.
![Gradiente formula](https://miro.medium.com/v2/resize:fit:1400/1*KIaYMmXnykZl_vjPUVjbyQ.png)

O resultado dessas derivadas irá retornar um vetor que leva em direção ao valor que pode maximizar a função.

Exemplo: https://www.youtube.com/watch?app=desktop&v=CbLkUxNv6Do

Mais: https://www.khanacademy.org/math/multivariable-calculus/multivariable-derivatives/partial-derivative-and-gradient-articles/a/the-gradient

### 2.0 Statics {#2.0-statics}

### 3.0 Linear Algebra {#3.0-linear-algebra}
