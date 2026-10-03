
> **Colunas calculadas armazenam seus valores no modelo de dados quando o Power BI carrega ou atualiza o modelo.**

---

## Como funciona uma coluna calculada?

Exemplo:

Tabela Vendas:

|Produto|Quantidade|Preço|
|---|---|---|
|A|2|10|
|B|3|20|

Você cria:

```
Total =
Vendas[Quantidade] * Vendas[Preço]
```

O Power BI calcula:

|Produto|Quantidade|Preço|Total|
|---|---|---|---|
|A|2|10|20|
|B|3|20|60|

---

Esses valores ficam armazenados.

O modelo passa a ter:

```
Tabela Vendas

Produto
Quantidade
Preço
Total  ← armazenado
```

---

# Quando esse cálculo acontece?

Durante:

## 1. Atualização dos dados (Refresh)

Exemplo:

Você atualiza o dataset:

```
Fonte de dados
      ↓
Power BI
      ↓
Calcula coluna
      ↓
Armazena resultado
```

---

## 2. Alteração da fórmula

Se você mudar:

Antes:

```
Total =
Quantidade * Preço
```

Depois:

```
Total =
Quantidade * Preço * 1.1
```

O Power BI recalcula a coluna inteira.

---

# Diferença para Medida

Essa é a pegadinha.

---

## Coluna calculada

Calculada:

```
No refresh
```

Armazenada:

```
Dentro do modelo
```

Exemplo:

```
Margem =
Vendas[Receita] - Vendas[Custo]
```

Cada linha possui um valor.

---

## Medida

Calculada:

```
Quando o usuário interage
```

Não é armazenada.

Exemplo:

```
Total Vendas =
SUM(Vendas[Valor])
```

Se o usuário filtra:

```
Ano = 2025
```

a medida recalcula.

---

# Comparação

||Coluna Calculada|Medida|
|---|---|---|
|Quando calcula?|Refresh|Consulta/visualização|
|Armazena valores?|✅ Sim|❌ Não|
|Calcula linha por linha?|✅ Sim|❌ Não necessariamente|
|Usa contexto de filtro?|❌ Não (normalmente)|✅ Sim|
|Consome memória?|✅ Sim|Pouco|

---

# Exemplo simples para memorizar

Imagine uma planilha Excel:

## Coluna calculada:

Você cria:

```
Preço × Quantidade
```

e grava o resultado em cada linha.

É como uma coluna nova na planilha.

---

## Medida:

É como:

```
= SOMA(Todas as vendas)
```

O resultado muda dependendo do filtro.