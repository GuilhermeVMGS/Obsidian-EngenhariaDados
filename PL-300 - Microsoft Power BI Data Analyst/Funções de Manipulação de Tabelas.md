# 1. NATURALINNERJOIN

## O que faz?

`NATURALINNERJOIN` junta duas tabelas usando **colunas com o mesmo nome e o mesmo tipo de dado**.

É parecido com um:

```
INNER JOIN
```

no SQL.

Sintaxe:

```
NATURALINNERJOIN(
    Tabela1,
    Tabela2
)
```

---

## Exemplo

Tabela Clientes:

|ClienteID|Nome|
|---|---|
|1|João|
|2|Maria|
|3|Pedro|

Tabela Compras:

|ClienteID|Valor|
|---|---|
|1|100|
|2|200|
|4|500|

Temos:

```
NATURALINNERJOIN(
    Clientes,
    Compras
)
```

Resultado:

|ClienteID|Nome|Valor|
|---|---|---|
|1|João|100|
|2|Maria|200|

Por quê?

Porque ele mantém apenas as linhas que existem nas duas tabelas.

O cliente 3 não aparece:

```
Clientes → existe
Compras → não existe
```

O cliente 4 não aparece:

```
Compras → existe
Clientes → não existe
```

---

# 2. NATURALLEFTOUTERJOIN

É parecido com o **LEFT JOIN do SQL**.

Sintaxe:

```
NATURALLEFTOUTERJOIN(
    Tabela1,
    Tabela2
)
```

Ele mantém **todas as linhas da primeira tabela**.

Exemplo:

```
NATURALLEFTOUTERJOIN(
    Clientes,
    Compras
)
```

Resultado:

|ClienteID|Nome|Valor|
|---|---|---|
|1|João|100|
|2|Maria|200|
|3|Pedro|BLANK|

O cliente Pedro aparece mesmo sem compra.

---

# Comparação rápida

|Função|SQL equivalente|Mantém|
|---|---|---|
|NATURALINNERJOIN|INNER JOIN|Somente correspondências|
|NATURALLEFTOUTERJOIN|LEFT JOIN|Tudo da primeira tabela + correspondências|

---

# Atenção: "Natural" significa o quê?

O DAX procura automaticamente:

- mesmo nome de coluna;
- mesmo tipo de dado.

Exemplo:

Tabela A:

|ProdutoID|
|---|
|10|

Tabela B:

|ProdutoID|
|---|
|10|

Ele usa essa coluna.

Mas:

Tabela A:

|IDProduto|
|---|
|10|

Tabela B:

|ProdutoID|
|---|
|10|

Não funciona automaticamente.

---

# 3. CROSSJOIN

Faz produto cartesiano.

Ou seja:

> Todas as combinações possíveis.

Exemplo:

Tabela Cores:

|Cor|
|---|
|Azul|
|Vermelho|

Tabela Tamanhos:

|Tamanho|
|---|
|P|
|M|
|G|

```
CROSSJOIN(
    Cores,
    Tamanhos
)
```

Resultado:

|Cor|Tamanho|
|---|---|
|Azul|P|
|Azul|M|
|Azul|G|
|Vermelho|P|
|Vermelho|M|
|Vermelho|G|

2 × 3 = 6 linhas.

Muito usado para criar combinações.

---

# 4. UNION

Junta tabelas verticalmente.

Parecido com:

```
UNION ALL
```

Exemplo:

Tabela Janeiro:

|Produto|Venda|
|---|---|
|A|100|

Tabela Fevereiro:

|Produto|Venda|
|---|---|
|A|200|

```
UNION(
 Janeiro,
 Fevereiro
)
```

Resultado:

|Produto|Venda|
|---|---|
|A|100|
|A|200|

Requisito:

As colunas precisam ter posições compatíveis.

---

# 5. INTERSECT

Retorna valores que existem nas duas tabelas.

Exemplo:

Tabela A:

```
1
2
3
```

Tabela B:

```
2
3
4
```

```
INTERSECT(A,B)
```

Resultado:

```
2
3
```

---

# 6. EXCEPT

Retorna o que existe na primeira tabela e não existe na segunda.

Exemplo:

```
EXCEPT(A,B)
```

A:

```
1
2
3
```

B:

```
2
3
4
```

Resultado:

```
1
```

---

# 7. TREATAS (muito importante na PL-300)

Não junta tabelas, mas cria uma relação virtual.

Exemplo:

Você tem:

```
Tabela Produtos

ProdutoID
```

e quer aplicar filtro em outra tabela.

```
CALCULATE(
    [Vendas],
    TREATAS(
        VALUES(OutraTabela[ProdutoID]),
        Produtos[ProdutoID]
    )
)
```

Ele fala:

> "Use esses valores como se fossem filtros nessa coluna."

Muito usado quando não existe relacionamento físico.

---

# Comparação para prova

| Função               | Ideia                                                         |
| -------------------- | ------------------------------------------------------------- |
| NATURALINNERJOIN     | Juntar tabelas pelas colunas iguais, somente correspondências |
| NATURALLEFTOUTERJOIN | Mantém toda primeira tabela                                   |
| CROSSJOIN            | Todas as combinações possíveis                                |
| UNION                | Empilhar tabelas                                              |
| INTERSECT            | Valores comuns                                                |
| EXCEPT               | Diferenças                                                    |
| TREATAS              | Criar filtro/relação virtual                                  |