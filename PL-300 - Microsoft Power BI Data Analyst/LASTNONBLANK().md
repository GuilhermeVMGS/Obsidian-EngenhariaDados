
Essa função retorna o **último valor não vazio** encontrado em uma coluna ou expressão.

Sintaxe:

```
LASTNONBLANK(
    coluna,
    expressão
)
```

Exemplo:

Tabela:

|Data|Venda|
|---|---|
|Jan|100|
|Fev|200|
|Mar|BLANK()|
|Abr|300|
|Mai|BLANK()|

Medida:

```
Última Venda =
LASTNONBLANK(
    Vendas[Data],
    SUM(Vendas[Venda])
)
```

Resultado:

```
Abr
```

Porque Abril foi a última data com valor.

---

Muito usado em:

- saldo de estoque;
- último preço;
- último evento;
- última atualização.

---

## Diferença para MAX()

MAX:

> pega o maior valor.

LASTNONBLANK:

> pega o último valor que possui dado.

Exemplo:

Datas:

```
Jan
Fev
Mar
Abr
```

Mas só Abril tem venda.

MAX(Data) pode retornar Abril.

Mas se houver datas futuras sem movimento:

```
Jan
Fev
Mar
Abr
Mai
Jun
```

MAX retorna Jun.

LASTNONBLANK retorna Abril.