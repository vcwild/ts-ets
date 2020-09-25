# ETS Models

- [Simple Exponential Smoothing Method](ses.ipynb)<br/>
- Holt's Linear Trend Method<br/>
- Exponential Trend Method<br/>
- Holt-Winters Seasonal Method

## Simple Exponential Smoothing

O método de previsão exponencial simples é viável em situações onde não haja tendência clara ou padrão sazonal.

O método de previsão é calculado multiplicando valores anteriores por pesos relativos, que são calculados baseados em um parâmetro de suavização $\alpha$. Essa será  a magnitude dos pesos aplicados aos valores anteriores da série, onde cada um dos pesos vai decrescendo exponencialmente conforme as observações vão ficando mais antigas. A fórmula geral será:

<img src="https://render.githubusercontent.com/render/math?math=Previsao = Peso_t\ Y_t \ %2B \ Peso_{t-1} Y_{t-1} %2B \ Peso_{t-2}\ Y_{t-2}\ %2B \ ...\ %2B \ (1-\alpha)^n Y_n" />

 Onde: <br/>
 ![formula](https://render.githubusercontent.com/render/math?math=t) : número de períodos anteriores ao atual (t=0 para o mais recente)<br/>
 ![formula](https://render.githubusercontent.com/render/math?math=Y_t) : valor da série temporal no período $t$<br/>
 ![formula](https://render.githubusercontent.com/render/math?math=Peso_t=\alpha(1-\alpha)^t)<br/>
 ![formula](https://render.githubusercontent.com/render/math?math=\alpha) : padrão de suavização entre 0 e 1<br/>
 ![formula](https://render.githubusercontent.com/render/math?math=n) : número total de períodos<br/>

## Double Exponential Smoothing (Holt's Linear Trend Method)

O método de suavização exponencial dupla é altamente viável em qualquer situação que não haja padrão sazonal no conjunto de dados.

É baseado no método SES, mas além de incluir o nível, também considera a tendência da série temporal no cálculo. Ele atinge essa possibilidade realizando dois cálculos de suavização, um para o nível de magnitude e outro para a tendência.

O cálculo de tendência é realizado de maneira linear ou aditiva, possibilitando que o resultado da predição não seja mais plano, mas que siga tendência positiva ou negativa.

## Exponential Trend Method

É uma variação do método linear de Holt. Porém considera que o nível e a tendência da série são aplicados de forma multiplicativa. Significando que a tendência da série irá crescer ou diminuir de forma exponencial, exibindo previsões numa taxa de crescimento de tendência fatorial

## Damped Trend Methods

É uma solução que apresenta parâmetros de amortecimento da linha de tendência, transformando-a em uma linha plana algum tempo no futuro, podendo ser aplicado de forma aditiva ou multiplicativa. 

O parâmetro de amortecimento é chamado $\Phi$, modelos com valores $\Phi$ pequenos pressupões que a tendência muda muito lentamente com o tempo, enquanto modelos com valores altos pressupões mudança rápida.