

Esse é um dos assuntos mais importantes de Time Intelligence.

---

## Primeiro conceito

As funções de inteligência temporal trabalham sobre uma:

Tabela Calendário.

Exemplo:

|Data|
|---|
|01/01/2024|
|02/01/2024|
|...|

---

## O que é SAMEPERIODLASTYEAR?

Ela retorna uma **tabela de datas**.

Isso é o mais importante.

Ela NÃO retorna:

- número;
- texto;
- data única.

Ela retorna uma tabela.

---

## Exemplo

Contexto atual:

```
Janeiro/2025
```

Ela retorna:

```
Janeiro/2024
```

Não apenas:

```
01/01/2024
```

Ela retorna todas as datas.

```
01

02

03

...

31
```

---

## Por isso ela é usada dentro do CALCULATE

Exemplo:

```
Vendas LY =
CALCULATE(
    [Vendas],
    SAMEPERIODLASTYEAR(Calendario[Data])
)
```

O CALCULATE muda o contexto.

---

Antes:

```
2025
```

Depois:

```
2024
```