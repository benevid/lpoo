# Processing em 1 hora

------

> A [Hora do Código](https://hourofcode.com/) é um desafio: gaste uma hora do seu tempo aprendendo a codificar. Você ficaria surpreso com o que você pode realizar nessa quantidade de tempo! A Hora do Código foi organizada pelo [Code.org](http://code.org/) como uma maneira de envolver mais pessoas na programação - especialmente pessoas que podem não se considerar cientistas da computação "típicos". A Hora do Código "oficial" ocorre durante a [Semana de Educação](http://csedweek.org/) em [Ciência da Computação,](http://csedweek.org/) em dezembro, mas você pode experimentá-la a qualquer momento!

## O que é programação?

A programação é o processo de escrever instruções que um computador pode seguir. Obviamente, os computadores não conseguem entender o inglês (ainda não), então essas instruções estão escritas em **código**. Existem diferentes idiomas para código, e usaremos um idioma chamado [Processing](https://processing.org/) . O **Processing** foi projetado para facilitar a criação de programas animados, interativos e artísticos. [Aqui](https://processing.org/exhibition/) estão alguns exemplos de programas escritos usando **Processing**.

Quando as pessoas pensam em código, geralmente pensam em zeros e zeros, mas há mais do que isso. O código permite criar praticamente qualquer coisa em que você possa pensar. É mais uma arte ou um ofício do que a maioria das pessoas imagina, e muitos artistas usam o código para se expressar.

> O **Processing** foi projetado com isso em mente.

## Funções

Você pode pensar no código como uma série de instruções. Pense em como você pode dar instruções de direção para outra pessoa:

```
drive 5 miles
turn left
drive 3 miles
```

A outra pessoa segue suas instruções e segue cada uma, uma após a outra. O código funciona da mesma maneira: você escreve instruções e o computador segue cada um, um de cada vez, um após o outro. Uma única instrução é chamada de **função** e você **chama funções** para informar ao computador o que fazer.

No seu editor Processing, digite esta linha de código e pressione o botão executar:

```
ellipse(50, 50, 75, 75);
```

E você deve ver isso:

![círculo](https://happycoding.io/tutorials/processing/images/hour-of-code-1.png)

Você também pode executar o código diretamente no navegador usando este editor incorporado:

> Parabéns por escrever sua primeira linha de código! ![: tada:](https://github.githubassets.com/images/icons/emoji/unicode/1f389.png) ![:balão:](https://github.githubassets.com/images/icons/emoji/unicode/1f388.png)

Essa linha de código é uma única instrução que **chama** a `ellipse()`função. A `ellipse()`função informa ao computador para desenhar um círculo, e os números entre `( )`parênteses indicam onde e qual o tamanho que deve ser desenhado. Tente alterar alguns dos números para ver o que cada um significa!

**Não esqueça o ponto e vírgula!** Assim como terminamos nossas frases com um `.`ponto final, finalizamos cada linha de código com um `;`ponto e vírgula. Esquecer de adicionar um ponto-e-vírgula é um dos erros de programação mais comuns; portanto, lembre-se disso ao escrever seu código.

## A página de referência do Processing

Deixe-me apresentar seu novo melhor amigo: [a referência do Processing](https://processing.org/reference/) . Esta página lista (quase) todas as funções que você pode chamar no Processing, e clicar em uma função fornece mais informações sobre quais parâmetros são necessários.

>  Isso pode parecer esmagador, mas você não precisa memorizar nada. Em vez disso, adicione esta página aos favoritos e venha aqui sempre que tiver curiosidade sobre como fazer algo. Essa deve ser sua primeira parada sempre que você estiver confuso ou precisar de mais informações.

Por exemplo, digamos que queremos ramificar e desenhar um retângulo. Começaríamos examinando a referência e procurando uma função que parecia promissora. (Se ainda não conseguimos encontrá-lo, podemos usar o “Processando desenhar retângulo” do Google, que nos levaria à página de referência específica.) Com certeza, encontraremos a [`rect()`](https://processing.org/reference/rect_.html)função!

Podemos ler [a `rect()`referência](https://processing.org/reference/rect_.html) para saber que ela usa os mesmos parâmetros da `ellipse()`função: um X, um Y, uma largura e uma altura. Com isso em mente, podemos adicionar um retângulo ao nosso programa:

```
ellipse(40, 40, 60, 60);
rect(40, 40, 50, 50);
```

![círculo e quadrado](https://happycoding.io/tutorials/processing/images/hour-of-code-2.png)



## Agora você é um programador.

No essencial, a programação é um **processo** de chegar a um objetivo, ler a documentação e fazer pesquisas no Google para aprender como atingir esse objetivo e depois escrever um código que atinja esse objetivo. A partir daqui, vamos fazer isso repetidamente.

Vamos aumentar nossa janela, mudar sua cor de fundo e colorir nossas formas. Antes de rolar para baixo e observar o código, tente encontrar as funções que executam cada uma dessas coisas e tente escrever o código você mesmo!

![círculo e quadrado maior e mais colorido](https://happycoding.io/tutorials/processing/images/hour-of-code-3.png)

Espero que você tenha encontrado a `size()`função que usa uma largura e altura da janela, a `background()`função que aceita valores de vermelho, verde e azul que se misturam para formar uma cor de fundo e a `fill()`função que também aceita valores de vermelho, verde e azul para colorir o formas. Nosso código pode ficar assim:

```
size(500, 500);

background(0, 0, 128);

fill(255, 0, 0);
ellipse(200, 200, 300, 300);

fill(0, 255, 0);
rect(200, 200, 250, 250);
```

Esse código chama a `size()`função para criar uma janela com 500x500 pixels em vez do padrão 100x100, depois chama a `background()`função e passa em três parâmetros. Os três parâmetros são valores de vermelho, verde e azul (também conhecidos como valores RGB) de 0 a 255 que se misturam para formar uma cor. Nesse caso, é apenas um valor azul de 128, que é azul escuro.

Em seguida, chama a `fill()`, que também aceita valores RGB, neste caso em vermelho. Pense nisso como mergulhar um pincel em tinta vermelha e depois usá-lo para pintar um círculo quando a `ellipse()`função for chamada na próxima linha. Em seguida, chama a `fill()`função novamente, desta vez passando com um valor RGB verde e, finalmente, usa esse pincel para pintar um retângulo verde.

## Exemplo: Cara sorridente

Aqui está um exemplo de programa que leva tudo o que aprendemos até agora (chegando a um objetivo, procurando coisas na referência e escrevendo código que atinja esse objetivo) e desenhando uma carinha sorridente:

```
size(200, 200);

//green
fill(0, 255, 0);

//draw the head
ellipse(100, 100, 150, 150);

//white
fill(255);

//draw the eyes
ellipse(75, 85, 30, 20);
ellipse(125, 85, 30, 20);

//black
fill(0);

//draw the pupils
ellipse(75, 85, 10, 10);
ellipse(125, 85, 10, 10);

//red
fill(255, 0, 0);

//draw the mouth
arc(100, 125, 80, 50, 0, 3.14);
line(60, 125, 140, 125);
```

As linhas que começam com `//`barras são **comentários** e são ignoradas pelo computador. Eles estão lá apenas para ajudarmos a entender nosso próprio código. Além disso, a `arc()`função provavelmente é nova para você, mas lembre-se de que você sempre pode consultar [a referência de processamento](https://processing.org/reference/) para saber mais sobre uma função!

Este código desenha um rosto sorridente:

![rosto sorridente](https://happycoding.io/examples/processing/calling-functions/images/smiley-face-1.png)

## Usando variáveis

Agora você sabe como chamar a `size()`função para alterar o tamanho da janela e sabe como passar parâmetros para funções como a `ellipse()`função para desenhar formas.

Digamos que queremos desenhar um círculo que ocupa toda a janela. Nós poderíamos fazer isso usando este código:

```
size(200, 200);
ellipse(100, 100, 200, 200);
```

![Círculo de 200 por 200 em janela de 200 por 200](https://happycoding.io/tutorials/processing/images/hour-of-code-4.png)

Este código chama a `size()`função para criar uma janela de 200 x 200 pixels. Em seguida, ele chama a `ellipse()`função e fornece um centro de `100,100`, que está no centro da `200x200`janela. Também fornece um tamanho de círculo `200x200`, ocupando toda a janela.

Mas e se quiséssemos alterar o tamanho da janela?

```
size(400, 400);
ellipse(100, 100, 200, 200);
```

Agora alteramos o tamanho da janela, mas não alteramos a posição ou o tamanho do nosso círculo. Pense em onde está a coordenada `100,100`em nossa janela de 200x200 e onde essa mesma coordenada está em uma janela de 400x400.

![Círculo de 200 por 200 em janela de 400 por 400](https://happycoding.io/tutorials/processing/images/hour-of-code-5.png)

Acabamos desenhando o cirlce no canto superior esquerdo da nossa janela. Para corrigir isso, poderíamos passar e alterar todos os parâmetros. Isso não seria muito ruim neste programa de exemplo, mas e o programa de carinhas felizes? Ou um programa ainda mais complicado, com centenas de linhas de código? Além disso, teríamos que repetir esse processo toda vez que alterássemos o tamanho da janela!

Não seria bom se o computador pudesse apenas lembrar o tamanho da janela e basear os parâmetros nisso? É para isso que servem as **variáveis** !

Depois que a `size()`função é chamada, podemos usar as variáveis `width`e `height`, que mantêm o tamanho da janela. Podemos usá-los exatamente como podemos usar valores. Podemos também usar **operadores** (coisas de matemática como `+`, `-`, `*`, e `/`) com variáveis. Assim, poderíamos reescrever nosso programa circular para usar variáveis em vez de **codificar** os parâmetros:

```
size(400, 400);
ellipse(width/2, height/2, width, height);
```

Agora nosso código usa o `width`e `height`variáveis. Usar `width/2`nos dá a meio caminho entre o lado esquerdo e direito da janela e `height/2`nos a meio caminho entre a parte superior e inferior da janela. Tente pensar em alguns exemplos de tamanhos de janelas, depois calcule `width/2`e `height/2`veja por que isso faz sentido. Os dois últimos parâmetros de `width`e `height`fazem o tamanho do círculo corresponder ao tamanho da janela.

O que acontece se você usar `size(200, 100)`ou `size(300, 600)`?

## Criando variáveis

Você não está limitado às variáveis `width`e `height`fornecidas pelo Processing. Você também pode criar suas próprias variáveis!

Para criar uma variável, você fornece um **tipo** , um **nome** e um **valor** . Se parece com isso:

```
float x = 50;
```

Essa linha de código cria uma variável `float` (o que significa que conterá um número) nomeado `x`que possui um valor de `50`. Agora você pode usar essa variável da mesma forma que as variáveis `width`e `height`:

```
float x = 50;
ellipse(x, 40, 25, 25);
```

Você pode criar quantas variáveis desejar:

```
float circleX = 50;
float circleY = 50;
float circleWidth = 75;
float circleHeight = 75;
ellipse(circleX, circleY, circleWidth, circleHeight);
```

![círculo](https://happycoding.io/tutorials/processing/images/hour-of-code-7.png)

Você também pode definir o valor de uma variável usando outras variáveis:

```
float circleX = width/2;
float circleY = height/2;
float circleWidth = width*.75;
float circleHeight = height*.75;
ellipse(circleX, circleY, circleWidth, circleHeight);
```

Este exemplo simples pode não parecer muito útil, mas as variáveis são úteis quando você deseja basear seu código em um valor que possa ser alterado. Um exemplo é ao usar a `random()`função

## A função `random()`

A `random()` fornece um número aleatório entre dois parâmetros a cada vez que você o chama, que pode ser passado para uma função como parâmetro ou armazenado em uma variável.

```
float x = random(0, 100);
//x is now a random number between 0 and 100
```

Isso pode não parecer muito útil, mas permite criar programas que fazem coisas diferentes toda vez que são executados ou gerar um comportamento novo e inesperado.

Por exemplo, este programa desenha um círculo colorido, colocado aleatoriamente e com tamanho aleatório toda vez que o programa é executado:

```
float circleX = random(0, width);
float circleY = random(0, height);
float circleSize = random(20, 100);
fill(random(0, 255), random(0, 255), random(0, 255));
ellipse(circleX, circleY, circleSize, circleSize);
```

![círculo aleatório](https://happycoding.io/tutorials/processing/images/hour-of-code-8.png) ![círculo aleatório](https://happycoding.io/tutorials/processing/images/hour-of-code-9.png) ![círculo aleatório](https://happycoding.io/tutorials/processing/images/hour-of-code-10.png)



## Criando Funções

Até o momento, o código que escrevemos é uma lista única de instruções que o computador segue e o programa é concluído.

Mas você também pode escrever um código chamado mais de uma vez, o que permite desenhar cenas que mudam com o tempo, criar animações ou interagir com o usuário. Você faz isso **criando funções** e, em seguida, colocando seu código (que chama outras funções) dentro dessas funções. Aqui está um exemplo:

```
void setup() {
  size(200, 200);
}

void draw() {
  fill(random(255), random(255), random(255));
  ellipse(random(width), random(height), 20, 20);
}
```

Este código cria duas funções: uma função `setup()` e uma função `draw()`. Dentro da `setup()`, o código cria uma janela de 200x200 e, na `draw()`, desenha um círculo colorido e colocado aleatoriamente.

> E aqui está a parte importante: O **Processing** executa automaticamente o código na função`setup()` uma vez no início de um programa e, em seguida, executa o código na função`draw()` 60 vezes por segundo.

Então agora, em vez de desenhar um único círculo aleatório, nosso programa desenha 60 círculos aleatórios a cada segundo!

![círculos aleatoriamente coloridos](https://happycoding.io/tutorials/processing/images/hour-of-code-12.png)

Tente adicionar uma chamada à função `background()` como a primeira linha dentro da `draw()`função para ver o que acontece.

## Animação

Agora você sabe como criar variáveis e como usar a função `draw()` para executar o código 60 vezes por segundo. Você pode combinar essas idéias para alterar o valor de uma variável ao longo do tempo, o que permite criar animações!

Você sabe que pode definir o valor de uma variável com base em outra variável:

```
float circleY = width/2;
```

Depois que uma variável é criada, você também pode definir seu valor com base em **si mesmo** , que usa seu valor antigo para criar um novo valor:

```
float circleY = 50;
circleY = circleY + 10;
//circleY is now 60
```

Se usarmos essa idéia com a função `draw()`, podemos alterar o valor de uma variável ao longo do tempo. E se basearmos nosso desenho nessa variável variável, nosso desenho mudará com o tempo, criando uma animação.

```
float circleY = 25;

void draw(){
  background(200);
  ellipse(50, circleY, 10, 10);
  
  circleY = circleY + 1;
}
```

Este código cria uma variável denominada `circleY`e a define `25`. Então, toda vez que a `draw()`função é chamada, o código desenha um plano de fundo cinza e, em seguida, desenha um círculo usando a `circleY`variável como sua posição vertical. Em seguida, o código é adicionado `1`à `circleY`variável Na próxima vez que a `draw()`função for chamada, ela `circleY`será um pouco mais alta, o que afastará o círculo da parte superior da tela.

Em outras palavras, parece que o círculo está caindo:

![círculo caindo](https://happycoding.io/tutorials/processing/images/animation-1.gif)

## Instruções If

Nossa animação não é muito interessante, porque assim que o círculo sai da tela, o programa termina. Seria bom se pudéssemos detectar quando o círculo sai da tela e fazer outra coisa, como redefinir o círculo ou até fazê-lo saltar. É aí que as instruções `if` são úteis.

Uma declaração `if` é uma maneira de fazer uma pergunta sim ou não e, em seguida, apenas executar código se a resposta for sim. Vamos adicionar um ao nosso programa:

```
float circleY = 25;

void draw(){
  background(200);
  ellipse(50, circleY, 20, 20);
  
  circleY = circleY + 1;
  
  if(circleY > height){
    circleY = 0; 
  }
}
```

Isso é exatamente como o programa anterior, exceto no final da função `draw()`, há uma declaração `if` que verifica se `circleY`é maior que `height`(em outras palavras, se o círculo caiu na parte inferior da janela). Nesse caso, redefine a variável `circleY` para `0`, o que move o círculo de volta para o topo da janela. Observe que a linha `circleY = 0` só acontece se `circleY`for maior que `height`, caso contrário, essa linha é ignorada!

![círculo caindo](https://happycoding.io/tutorials/processing/images/animation-2.gif)

Mas não estamos limitados a círculos em queda! Vamos ver outro exemplo:

#### **Exemplo: Random Walker**

```java
float x;
float y;
float shade;

void setup() {
  size(200, 100);
  
  //start in middle of screen
  x = width/2;
  y = height/2;
  shade = 128;
}

void draw() {
    
  //randomly move the point
  x = x + random(-1, 1);
  y = y + random(-1, 1);
  
  //wrap left and right
  if(x < 0){
    x = width;
  }
  if(x > width){
    x = 0;
  }

  //wrap top and bottom
  if(y < 0){
    y = height;
  }
  if(y > height){
    y = 0;
  }
  
  //randomly change the color
  shade = shade + random(-1, 1);
  
  //don't let the color go outside the bounds
  if(shade < 0){
    shade = 0;
  }
  if(shade > 255){
    shade = 255;
  }
  
  //set the color
  stroke(shade);
  
  //draw the point
  point(x, y);
}
```

Este programa armazena um ponto nas variáveis `x`e `y`, bem como um tom de cinza na variável `shade`. Em seguida, na função `draw()`, o código aumenta ou diminui aleatoriamente as variáveis `x`e `y`, e usa instruções `if` para agrupar o ponto para o outro lado quando ele sai da tela. Da mesma forma, o código aumenta ou diminui aleatoriamente a variável `shade` e usa a instruções`if` para impedir que saia dos limites de 0 a 255. Então, simplesmente desenha o ponto.

Isso é feito 60 vezes por segundo, o que resulta em "rabiscos" aleatoriamente na tela. Não é muito emocionante de assistir, mas se você deixar rodar por um tempo, isso resultará em cenas legais como esta:

![rabiscos em preto e branco](https://happycoding.io/examples/processing/animation/images/random-walker-4.png)

Tente escrever um código que adicione cores!

![rabiscos coloridos](https://happycoding.io/examples/processing/animation/images/random-walker-3.png)



Este é um algoritmo real chamado [caminhante aleatório](https://en.wikipedia.org/wiki/Random_walker_algorithm) e possui muitos usos na vida real. [:arte:](https://github.githubassets.com/images/icons/emoji/unicode/1f3a8.png)

## Entrada do Usuário

Até agora, nossos programas não foram interativos. Eles envolveram aleatoriedade, mas não reagiram a nada que o usuário faça. Vamos adicionar um código que interaja com o usuário movendo o mouse!

Da mesma forma que as variáveis `width`e `height`armazenam o tamanho da janela, as variáveis `mouseX`e `mouseY`mantêm a posição atual do mouse. Podemos usar essas variáveis para desenhar coisas onde o mouse está:

```
void setup() {
  size(400, 200);
}

void draw() {  
  ellipse(mouseX, mouseY, 50, 50);
}
```

Esse código simplesmente desenha um círculo onde quer que o mouse esteja.

![círculo do mouse](https://happycoding.io/tutorials/processing/images/input-5.gif)

> Tente alterar esse código para que o círculo persiga o mouse em vez de desenhar em cima dele! **Dica:** armazene a posição do círculo em variáveis e altere-as usando `if`instruções baseadas em se são maiores ou menores que as coordenadas do mouse.

Existem várias outras variáveis (e funções) que você pode usar para interagir com o usuário. Outro exemplo é a `mousePressed`, que você pode usar com uma instrução `if` para executar quando o usuário está pressionando o mouse:

```
void setup() {
  size(400, 200);
}

void draw() {  
  if(mousePressed){
    ellipse(mouseX, mouseY, 50, 50);
  }
}
```

Agora, nosso código só desenha um círculo se o mouse for pressionado, o que transforma isso em um programa de desenho simples!



## Créditos

[Happy Coding is open source](http://happycoding.io/license.html)

https://happycoding.io/tutorials/processing/hour-of-code

[kevin@HappyCoding.io](mailto:kevin@HappyCoding.io)

