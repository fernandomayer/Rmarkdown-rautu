# Um documento em Markdown

## Sobre o Markdown

O Markdown é uma linguagem de marcação muito simples, desenvolvida por
John Gruber.

A ideia básica por trás da linguagem é fazer com que o escritor se
preocupe mais com o **conteúdo** do texto do que com a *formatação*.

## Mais um título

Aqui vamos tentar descrever uma análise.

## Simulando variáveis aleatórias

No R podemos simular valores de uma distribuição normal padrão através
da função `rnorm()`.

Seja $X \sim \text{N}(0,1)$, então para gerar 30 valores dessa variável
aleatório normal, fazemos


```r
(x <- rnorm(30))
```

```
##  [1] -0.12205483 -0.03192995 -1.34250710 -0.03160451 -1.09346653
##  [6]  1.42059185  0.17443779 -0.59232571  0.50222819 -1.45559274
## [11] -0.29034075 -0.74931517 -1.02330612  1.16306035  0.15796895
## [16]  0.68389293 -1.18105355 -1.57944493  0.08298691 -0.25453813
## [21] -0.33358033 -1.07729716 -2.32986238 -0.08540871  0.06145901
## [26]  0.40928553  0.90874817 -1.31408942 -1.67941077  0.98797274
```

## Comentários

Com o resultado dessa simulação, podemos calcular a média e a variância
dessa VA $X$ para conferir se o resultado fica próximo de 0 e 1,
respectivamente.

## Visualização

Também podemos fazer um histograma dessa VA $X$ simulada


```r
hist(x)
```

![plot of chunk unnamed-chunk-2](figure/unnamed-chunk-2-1.png) 

