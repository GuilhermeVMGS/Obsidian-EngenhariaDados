
Essa função altera a direção do filtro de um relacionamento **durante uma medida**.

Sintaxe:

```
CROSSFILTER(
    Coluna1,
    Coluna2,
    Direção
)
```

---

Imagine:

```
DimCliente
     |
     |
FatoVendas
```

Normalmente:

```
Cliente → Vendas
```

Filtro vai apenas nessa direção.

---

Agora você quer temporariamente:

```
Cliente ↔ Vendas
```

Usa:

```
CALCULATE(
    [Total Vendas],
    CROSSFILTER(
        Cliente[ID],
        Vendas[ID],
        BOTH
    )
)
```

---

Direções:

### NONE

Desativa relacionamento.

```
NONE
```

---

### ONEWAY

Uma direção:

```
Cliente → Vendas
```

---

### BOTH

Bidirecional:

```
Cliente ↔ Vendas
```

---

Quando usar?

	Quando você precisa alterar comportamento de filtro somente em uma medida.