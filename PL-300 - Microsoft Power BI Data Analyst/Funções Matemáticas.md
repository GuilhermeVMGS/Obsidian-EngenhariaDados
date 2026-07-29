

### COUNTAX

O **COUNTAX** é uma função DAX usada para **contar resultados não vazios de uma expressão avaliada linha por linha em uma tabela**.

A parte mais importante:

> **COUNTAX primeiro percorre uma tabela, calcula uma expressão para cada linha e depois conta quantos resultados não são vazios.**

---

# Sintaxe

```
COUNTAX(
    <Tabela>,
    <Expressão>
)
```

Exemplo:

```
COUNTAX(
    Vendas,
    Vendas[Valor]
)
```

Ele faz:

1. Vai linha por linha da tabela `Vendas`;
2. Avalia `Vendas[Valor]`;
3. Conta quantos resultados existem.