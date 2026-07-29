
### PERCENTILEX.INC

## O que é?

`PERCENTILEX.INC` calcula um **percentil usando uma expressão avaliada linha por linha em uma tabela**.

Ela pertence à família de funções iteradoras (`X`).

Sintaxe:

```
PERCENTILEX.INC(
    Tabela,
    Expressão,
    Percentil
)
```

---

## Exemplo

Tabela:

|Produto|Vendas|
|---|---|
|A|100|
|B|200|
|C|300|
|D|400|

Queremos o:

```
Percentil 75%
```

Medida:

```
P75 =
PERCENTILEX.INC(
    Vendas,
    Vendas[Valor],
    0.75
)
```

Resultado:

O Power BI calcula o ponto onde 75% dos valores estão abaixo.

---

## O que significa INC?

INC = Inclusive

Inclui:

- mínimo;
- máximo.

Existe também:

```
PERCENTILEX.EXC
```

que usa método exclusivo.

---

## Diferença para PERCENTILE

### PERCENTILE.INC

Usa uma coluna.

Ex:

```
PERCENTILE.INC(
    Vendas[Valor],
    0.75
)
```

---

### PERCENTILEX.INC

Usa uma expressão.

Ex:

```
PERCENTILEX.INC(
    Vendas,
    Vendas[Quantidade] * Vendas[Preço],
    0.75
)
```

---

# Uso real:

Exemplo:

> "Qual valor representa os 25% maiores clientes?"

Pode usar percentis.