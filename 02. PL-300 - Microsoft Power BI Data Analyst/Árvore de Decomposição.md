
- 🌳 **Árvore de Decomposição = investigar o PORQUÊ**
- 🔽 **Funil = acompanhar um FLUXO e suas perdas**

![[Pasted image 20260730172456.png]]

# 1. O que é a Árvore de Decomposição (Decomposition Tree)?

A **Árvore de Decomposição** é um visual do Power BI usado para **analisar uma métrica e descobrir quais fatores influenciam esse resultado**.

A pergunta que ela responde é:

> "Por que esse valor é alto ou baixo?"

ou:

> "Quais dimensões explicam esse resultado?"

---

## Exemplo prático

Você tem:

Medida:

```
Vendas Totais = SUM(Vendas[Valor])
```

Resultado:

```
Vendas Totais = R$ 10 milhões
```

O gerente pergunta:

> "Por que vendemos R$ 10 milhões?"

Você pode decompor:

```
Vendas Totais
      |
      |
      +-- Região
             |
             +-- Sudeste
             |
             +-- Sul
             |
             +-- Nordeste
```

Depois:

```
Sudeste
    |
    +-- Produto
          |
          +-- Notebook
          +-- Celular
```

Depois:

```
Notebook
    |
    +-- Loja
```

Ela vai "quebrando" a medida.

---

# Visualmente:

Imagine:

```
Vendas
100 milhões

        Região

 ┌─────────────┐
 │             │
Sul          Sudeste
20M            80M

               Produto

          ┌───────────┐
          Notebook   Celular
          50M        30M
```

---

# 2. O que são as dimensões?

Dimensão é um campo usado para explicar a métrica.

Exemplo:

Medida:

```
Faturamento
```

Dimensões:

```
Região
Produto
Cliente
Vendedor
Canal de venda
```

A árvore tenta responder:

> "Qual dessas dimensões explica melhor o faturamento?"

---

# 3. O que são as "divisões por IA"?

Na Árvore de Decomposição existem dois tipos de divisão:

## Expanda manualmente

Você escolhe:

```
Analisar por:
Produto
```

Você controla.

---

## AI Split (Divisão por IA)

Você deixa o Power BI escolher:

> "Qual campo devo analisar agora para explicar melhor esse valor?"

Exemplo:

Você tem:

Medida:

```
Lucro = R$ 5 milhões
```

Dimensões disponíveis:

- Região
- Produto
- Vendedor
- Canal

O Power BI analisa:

```
Qual desses campos mais explica a variação do lucro?
```

E sugere:

```
Produto
```

---

# 4. Qual técnica estatística ele usa?

A resposta correta é:

✅ **D. Calcula a significância estatística para identificar o campo que mais contribui para a variância na medida analisada.**