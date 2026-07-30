
# O que é um gráfico de dispersão (Scatter Chart)?

O gráfico de dispersão serve para mostrar a **relação entre variáveis numéricas**.

Em vez de barras ou linhas, ele utiliza **pontos**.

Exemplo:

Cada ponto representa um cliente.

```
          Uso de Dados (GB)
40 |                         •
35 |                   •
30 |              •
25 |        •
20 |   •
15 |
10 |
 5 |
 0 +----------------------------------------
      100    200    300    400    500
          Minutos de ligação
```

Cada bolinha = um cliente.

---

# O que cada eixo representa?

Normalmente:

## Eixo X

Uma medida numérica.

Exemplo:

```
Minutos Mensais
```

---

## Eixo Y

Outra medida numérica.

Exemplo:

```
Uso de Dados
```

---

Então um cliente pode ser:

```
Minutos = 320

Dados = 18 GB
```

Ele aparece aqui:

```
            •
```

---

# O que cada bolinha representa?

Cada bolinha é uma categoria do campo **Detalhes**.

Exemplo:

Detalhes:

```
ClienteID
```

Então:

```
Cliente 1

Cliente 2

Cliente 3

...
```

Cada um vira um ponto.

Sem "Detalhes", o Power BI agregaria os dados e você poderia ver apenas um ponto.

---

# Tamanho da bolha

Você pode colocar uma terceira medida.

Exemplo:

```
Valor Gasto
```

Cliente A:

```
R$ 50
```

Bolha pequena.

Cliente B:

```
R$ 1.000
```

Bolha grande.

---

# Cor

Pode representar uma quarta dimensão.

Exemplo:

Estado.

```
Azul = SP

Verde = MG

Vermelho = RJ
```

---

# Reprodução (Play Axis)

Existe ainda um eixo de reprodução.

Exemplo:

Ano.

```
2023

↓

2024

↓

2025
```

As bolhas vão se movimentando.

---

# Então quantas dimensões o Scatter consegue mostrar?

Até cinco:

|Dimensão|Campo|
|---|---|
|1|X|
|2|Y|
|3|Tamanho|
|4|Cor (Legenda)|
|5|Tempo (Play Axis)|

Por isso ele é chamado de visual multidimensional.

---

# Quando usar?

Quando você quer descobrir:

- padrões;
- correlações;
- outliers;
- agrupamentos.

---

Exemplo:

Altura × Peso.

```
Peso

^

|

|

|

+-------------------->

Altura
```

Você rapidamente vê pessoas muito diferentes.

---

# O que é Clustering?

Agora vem a parte importante da questão.

Imagine 40.000 clientes.

Você não sabe quantos tipos de clientes existem.

Visualmente você vê algo assim:

```
•••••

•••••

•••••



             •••••

             •••••



                         •••••

                         •••••
```

Você percebe:

"Parece que existem três grupos."

Mas ninguém informou isso.

---

Quem descobre?

O algoritmo de Clustering.

---

# Como funciona?

O Power BI utiliza um algoritmo semelhante ao **K-Means**.

Ele analisa:

- distância entre pontos;
- proximidade;
- semelhança.

Depois cria grupos automaticamente.

Exemplo:

```
Grupo 1

Grupo 2

Grupo 3
```

---

# Como fazer no Power BI?

Você cria um Scatter Chart.

Depois:

Painel:

```
Analytics

↓

Find Clusters
```

ou

```
Localizar Agrupamentos
```

O Power BI cria uma nova categoria:

```
Cluster 1

Cluster 2

Cluster 3
```

Essa categoria pode ser usada em outros visuais.

---

# Por que precisa ser Scatter Chart?

Porque o algoritmo trabalha com coordenadas.

Cada cliente vira um ponto.

Exemplo:

Cliente:

```
X = minutos

Y = dados
```

O algoritmo mede distâncias entre pontos.

Em uma tabela isso não faz sentido visualmente.