
# Número Decimal (Decimal Number)

Também chamado de:

> **Floating Point Number** (ponto flutuante)

É o tipo usado para números que podem ter muitas casas decimais e uma faixa muito grande de valores.

Exemplos:

```
10,5

3,14159265

0,0000001

99999999999,123456
```

No Power BI, ele utiliza o padrão **IEEE 754 Double Precision** (64 bits).

---

## Vantagem

Suporta:

- números muito grandes;
- números muito pequenos;
- muitas casas decimais.

---

## Desvantagem

Como é um número de **ponto flutuante**, alguns valores **não conseguem ser representados exatamente**.

Exemplo clássico:

```
0,1 + 0,2
```

Você esperaria:

```
0,3
```

Mas internamente pode virar algo como:

```
0,30000000000000004
```

Isso acontece porque o computador armazena o número em binário.

É uma limitação do formato IEEE 754, não do Power BI.

---

# Número Decimal Fixo (Fixed Decimal Number)

Também chamado de:

> **Currency** (Moeda)

Mesmo que você não esteja trabalhando com dinheiro.

Ele usa um formato diferente.

Em vez de ponto flutuante, ele armazena o valor como um **inteiro escalado**.

Exemplo:

```
10,25
```

Internamente fica algo parecido com:

```
102500
```

(com fator de escala de 10.000)

Depois o Power BI apenas coloca a vírgula de volta.

---

## Resultado

O número fica **exato**.

Exemplo:

```
0,1 + 0,2
=
0,3
```

Sem erro de arredondamento.

---

# Quantas casas decimais?

Número Decimal Fixo suporta até **4 casas decimais**.

Exemplos:

```
10,1234
```

OK.

---

```
10,12345
```

Será arredondado.

---

# Comparação

|Característica|Número Decimal|Número Decimal Fixo|
|---|---|---|
|Tipo interno|Ponto flutuante (Double)|Inteiro escalado (Currency)|
|Precisão|Pode ter pequenos erros|Exata (até 4 casas decimais)|
|Casas decimais|Muitas|Até 4|
|Melhor para|Medições científicas, taxas, cálculos gerais|Valores financeiros, monetários e contábeis|

---

# Exemplo prático

Imagine vendas.

Preço:

```
19,99
```

Quantidade:

```
3
```

Total:

```
59,97
```

Você quer que fique exatamente:

```
59,97
```

Use:

✅ Número Decimal Fixo

---

Agora imagine:

Temperatura:

```
22,15378456
```

ou

Coordenadas GPS:

```
-19,924501
```

ou

Medições científicas.

Use:

✅ Número Decimal

---

# Qual ocupa menos espaço?

Na prática, ambos ocupam **8 bytes** no Power BI.

A diferença **não é memória**, e sim:

- precisão;
- forma de armazenamento.

---

# Quando usar cada um?

## Número Decimal

Use quando:

- precisa de muitas casas decimais;
- pequenas diferenças de precisão não são críticas.

Exemplos:

- temperatura;
- latitude;
- longitude;
- medições;
- probabilidades.