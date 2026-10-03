
# 1. INNER JOIN (Junção Interna)

## Ideia:

> Retorna apenas registros que existem nas duas tabelas.

Ou seja:

"Quero somente quem tem correspondência."

Resultado:

|ID|Cliente|Produto|
|---|---|---|
|1|João|Notebook|
|2|Maria|Mouse|

Pedro e Ana não aparecem porque não têm compra.

---

## Quando usar?

Quando você quer apenas dados completos.

Exemplo:

"Liste clientes que fizeram compras."

Resposta:

✅ INNER JOIN

---

# 2. LEFT JOIN / LEFT OUTER JOIN

Esses dois são a **mesma coisa**.

No SQL:

```
LEFT JOIN
```

é uma abreviação de:

```
LEFT OUTER JOIN
```

---

## Ideia:

> Mantém tudo da tabela da esquerda e traz correspondências da direita.

Resultado:

|ID|Cliente|Produto|
|---|---|---|
|1|João|Notebook|
|2|Maria|Mouse|
|3|Pedro|NULL|
|4|Ana|NULL|

Pedro e Ana aparecem, mesmo sem compra.

---

## No Power Query:

Nome:

```
Left Outer
```

É o mesmo conceito.

---

## Quando usar?

Exemplo:

"Quero todos os clientes e mostrar suas compras quando existirem."

✅ LEFT OUTER

---

# 3. RIGHT JOIN / RIGHT OUTER JOIN

É o contrário do LEFT.

> Mantém tudo da tabela da direita e traz correspondências da esquerda.

Resultado:

|ID|Cliente|Produto|
|---|---|---|
|1|João|Notebook|
|2|Maria|Mouse|
|5|NULL|Teclado|

A compra do ID 5 aparece, mesmo sem cliente.

---

Na prática é menos usado porque você pode inverter a ordem das tabelas e usar LEFT JOIN.

---

# 4. FULL OUTER JOIN

Também chamado:

```
FULL JOIN
```

## Ideia:

> Mantém tudo dos dois lados.

Resultado:

|ID|Cliente|Produto|
|---|---|---|
|1|João|Notebook|
|2|Maria|Mouse|
|3|Pedro|NULL|
|4|Ana|NULL|
|5|NULL|Teclado|

Ele traz:

- correspondências;
- registros sem correspondência da esquerda;
- registros sem correspondência da direita.

---

## Quando usar?

Para encontrar diferenças entre tabelas.

Exemplo:

"Compare clientes cadastrados no sistema A e sistema B."

---

# 5. LEFT ANTI JOIN

Esse é muito usado no Power Query.

## Ideia:

> Retorna apenas registros da esquerda que NÃO possuem correspondência na direita.

Resultado:

|ID|Cliente|
|---|---|
|3|Pedro|
|4|Ana|

Ou seja:

"Quais clientes nunca compraram?"

---

## Uso:

- Encontrar faltantes
- Validar dados
- Auditoria

---

# 6. RIGHT ANTI JOIN

É o contrário:

> Retorna registros da direita que não existem na esquerda.

Resultado:

|ID|Produto|
|---|---|
|5|Teclado|

---

# 7. LEFT SEMI JOIN

Esse aparece menos, mas existe.

## Ideia:

> Retorna apenas linhas da esquerda que possuem correspondência na direita, mas sem trazer colunas da direita.

Exemplo:

Clientes que compraram:

|ID|Cliente|
|---|---|
|1|João|
|2|Maria|

Mas não traz:

```
Produto
```

---

# 8. RIGHT SEMI JOIN

Mesmo conceito, invertendo os lados.

---

# Resumo para PL-300

| JOIN                     | Resultado                                        |
| ------------------------ | ------------------------------------------------ |
| INNER                    | Somente correspondências                         |
| LEFT OUTER / LEFT JOIN   | Tudo da esquerda + correspondências da direita   |
| RIGHT OUTER / RIGHT JOIN | Tudo da direita + correspondências da esquerda   |
| FULL OUTER               | Tudo dos dois lados                              |
| LEFT ANTI                | Esquerda sem correspondência                     |
| RIGHT ANTI               | Direita sem correspondência                      |
| LEFT SEMI                | Esquerda com correspondência, sem trazer direita |
| RIGHT SEMI               | Direita com correspondência, sem trazer esquerda |