
Cardinalidade define a relação entre tabelas.

> **Quanto maior o nível de detalhe de uma tabela, normalmente maior será a cardinalidade das suas colunas.**

Mas vamos separar os conceitos.

---

# 1. O que é cardinalidade?

Cardinalidade de uma coluna é a **quantidade de valores únicos (distintos)** que ela possui.

Exemplo:

Tabela de vendas:

|VendaID|Produto|Estado|Data|
|---|---|---|---|
|1|Arroz|MG|01/01|
|2|Arroz|MG|02/01|
|3|Feijão|SP|02/01|
|4|Arroz|RJ|03/01|

Cardinalidade:

|Coluna|Valores distintos|Cardinalidade|
|---|---|---|
|VendaID|1,2,3,4|4 (alta)|
|Produto|Arroz, Feijão|2 (baixa)|
|Estado|MG, SP, RJ|3 (baixa)|
|Data|3 datas|3|

---

# 2. O que é nível de detalhe (granularidade)?

É **o quão específica é uma linha da tabela**.

Exemplo:

## Alta granularidade (muito detalhe)

Tabela de vendas transacionais:

|Data|Cliente|Produto|Quantidade|
|---|---|---|---|
|01/01|João|Arroz|2|
|01/01|Maria|Arroz|1|
|01/02|João|Feijão|3|

Cada linha representa:

> Uma venda individual.

---

## Baixa granularidade (mais agregado)

Tabela resumida:

|Mês|Produto|Total|
|---|---|---|
|Jan|Arroz|5000|
|Jan|Feijão|3000|

Cada linha representa:

> Total de vendas por mês/produto.

---

# 3. Então quanto mais agregada, menor a cardinalidade?

**Geralmente sim.**

Porque quando você agrega, você reduz a quantidade de combinações possíveis.

Veja:

## Tabela original (detalhada)

Fato_Vendas:

|Data|Cliente|Produto|Venda|
|---|---|---|---|
|01/01|João|Arroz|10|
|01/01|Maria|Arroz|20|
|01/01|João|Feijão|30|
|02/01|Carlos|Arroz|15|

Combinações:

```
Data + Cliente + Produto
```

Tem muitas possibilidades.

---

## Tabela agregada:

Fato_Vendas_Mensal:

|Mês|Produto|Venda|
|---|---|---|
|Jan|Arroz|45|
|Jan|Feijão|30|

Agora:

```
Mês + Produto
```

Tem poucas combinações.