# Um documento em Markdown

## Sobre o Markdown

O Markdown é uma linguagem de marcação muito simples, desenvolvida por
John Gruber.

A ideia básica por trás da linguagem é fazer com que o escritor se
preocupe mais com o **conteúdo** do texto do que com a *formatação*.

## Mais um título

Aqui vamos tentar descrever uma análise.

### Simulando variáveis aleatórias

No R podemos simular valores de uma distribuição normal padrão através
da função `rnorm()`.

Seja $X \sim \text{N}(0,1)$, então para gerar 30 valores dessa variável
aleatório normal, fazemos

```
x <- rnorm(30)
```

Com o resultado dessa simulação, podemos calcular a média e a variância
dessa VA $X$ para conferir se o resultado fica próximo de 0 e 1,
respectivamente.

Também podemos fazer um histograma dessa VA $X$ simulada

```
hist(x)
```

### Análise de dados

Abaixo tem-se o ajuste do modelo de regressão linear simples

$$
Y = \beta_0 + \beta_1 x + \epsilon
$$

para dados de distância para parada completa de um veículo em função da
velocidade no instante de acionamento dos freios. Esse conjunto de dados
está objeto `cars`.

```
## Carrega o conjunto de dados
data(cars)

## Resumo dos dados
summary(cars)
```

Os parâmetros do modelo linear podem ser obtidos pela função `lm()`

```
## Ajuste do modelo
mod <- lm(dist ~ speed, data = cars)
## Resumo do modelo
summary(mod)
```

Antes de interpretar o modelo e fazer inferência, é importante que sejam
verificados os pressupostos considerados através da análise dos resíduos.

```
par(mfrow = c(2, 2))
plot(mod)
par(mfrow = c(1,1))
```

Assumindo que o ajuste do modelo está adequado, pode-se obter o 
gráfico dos valores preditos sobre o diagrama de dispersão dos
valores observados.

```
## Intervalo de valores para predição
pred <- data.frame(speed = seq(4, 25, by = 0.5))
## Valores preditos
ypred <- predict(mod, newdata = pred, interval = "confidence")
## Inclui valores preditos no data frame
pred <- cbind(pred, ypred)
```

Agora podemos visualizar o modelo ajustado aos dados

```
## Gráfico de dispersão
plot(dist ~ speed, data = cars,
     xlab = "Velocidade ao acionar os freios",
     ylab = "Distância para parada completa")
## Intervalo de predição
with(pred,
     matlines(x = speed, y = cbind(fit, lwr, upr),
              lty = c(1, 2, 2), col = 1))
```

A inclinação desse modelo linear é 3.9324088.
