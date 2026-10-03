
# Primeiro: existem dois "planos de consulta" diferentes no ecossistema Power BI

Isso confunde muita gente na PL-300.

## 1) Plano de Consulta do Power Query ❌ (não é essa questão)

Usado para analisar:

- Query Folding
- etapas M
- se uma transformação vai para a fonte

Exemplo:

```
Power Query
    ↓
SQL Server
    ↓
Consulta nativa
```

Pergunta que responde:

> "Minha transformação está sendo enviada para a origem?"

---

## 2) Plano de Consulta DAX ✅ (essa questão)

Usado na **Exibição de Consulta DAX (DAX Query View)**.

Ele analisa:

> "Como o mecanismo do Power BI executa essa consulta DAX?"

---

# O que é uma consulta DAX?

É uma instrução enviada ao modelo semântico para buscar dados.

Exemplo:

```
EVALUATE
SUMMARIZE(
    Vendas,
    Produto[Categoria],
    "Total", SUM(Vendas[Valor])
)
```

O Power BI precisa executar isso.

O plano mostra:

- quais operações serão feitas
- em qual ordem
- como o mecanismo vai resolver a consulta

---

# O que são operações lógicas e físicas?

Essa é a parte da alternativa correta.

O Power BI possui dois níveis de execução:

---

# 1. Plano lógico

Mostra a intenção da consulta.

Exemplo:

```
Agrupar vendas por categoria

↓

Calcular soma

↓

Retornar resultado
```

É o "o que precisa ser feito".

---

# 2. Plano físico

Mostra como o motor realmente executa.

Exemplo:

```
Storage Engine Scan
        ↓
Aggregation
        ↓
Formula Engine Calculation
```

É o "como será feito".

---

# Exemplo prático

Você cria uma medida:

```
Total Vendas =
SUM(Vendas[Valor])
```

No visual:

```
Categoria | Total
-----------------
Notebook  | 50000
Celular   | 70000
```

O Plano de Consulta DAX pode mostrar algo como:

```
Scan tabela Vendas

↓

Aplicar filtro Categoria

↓

Agregação SUM

↓

Retornar resultado
```