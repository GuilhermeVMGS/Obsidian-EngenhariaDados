
A função **PARALLELPERIOD** é uma função de inteligência de tempo do DAX usada para **deslocar um período de tempo para outro período equivalente**, retornando uma tabela de datas.

Ela é muito usada para comparar períodos, como:

- mês atual vs mês anterior
- ano atual vs ano anterior
- trimestre atual vs trimestre anterior

---

# Sintaxe

```
PARALLELPERIOD(
    <dates>,
    <number_of_intervals>,
    <interval>
)
```

## Parâmetros

### 1. `<dates>`

É a coluna de datas que será deslocada.

Normalmente:

```
Calendario[Data]
```

Importante:

Deve vir de uma **tabela calendário**.

---

### 2. `<number_of_intervals>`

Define quantos períodos mover.

Pode ser:

- positivo → futuro
- negativo → passado

Exemplo:

```
-1
```

Significa:

voltar 1 período.

---

### 3. `<interval>`

Define o tipo de deslocamento.

Aceita:

```
YEAR
QUARTER
MONTH
```

---

# Exemplo básico

Temos uma tabela:

## Calendário

|Data|
|---|
|01/01/2025|
|02/01/2025|
|...|
|31/01/2025|

Medida:

```
Vendas Ano Anterior =
CALCULATE(
    [Total Vendas],
    PARALLELPERIOD(
        Calendario[Data],
        -1,
        YEAR
    )
)
```

---

O que acontece?

Imagine que o filtro atual seja:

```
Ano = 2026
```

O Power BI recebe:

```
PARALLELPERIOD(
    Calendario[Data],
    -1,
    YEAR
)
```

Ele retorna:

```
Ano = 2025
```

Então o CALCULATE calcula:

```
Vendas de 2025
```

---

# Relação com CALCULATE

Normalmente usamos assim:

```
Medida =
CALCULATE(
    [Métrica],
    PARALLELPERIOD(...)
)
```

Porque:

- PARALLELPERIOD retorna uma tabela de datas
- CALCULATE altera o contexto de filtro

Fluxo:

```
Contexto atual
       |
       ↓
PARALLELPERIOD desloca datas
       |
       ↓
CALCULATE aplica novo filtro
       |
       ↓
Nova métrica
```

---

# Exemplo: Comparação YoY

Queremos:

"Crescimento das vendas em relação ao ano anterior"

Primeiro:

```
Vendas LY =
CALCULATE(
    [Vendas],
    PARALLELPERIOD(
        Calendario[Data],
        -1,
        YEAR
    )
)
```

Depois:

```
Crescimento YoY =
DIVIDE(
    [Vendas] - [Vendas LY],
    [Vendas LY]
)
```

Resultado:

|Ano|Vendas|Ano anterior|Crescimento|
|---|---|---|---|
|2026|120 mil|100 mil|20%|

---

# PARALLELPERIOD x SAMEPERIODLASTYEAR

Essa comparação cai bastante na PL-300.

---

# SAMEPERIODLASTYEAR

Exemplo:

```
CALCULATE(
    [Vendas],
    SAMEPERIODLASTYEAR(Calendario[Data])
)
```

Significa:

> Pegue exatamente o mesmo período do ano passado.

Exemplo:

Filtro atual:

```
15/07/2026
```

Retorna:

```
15/07/2025
```

---

# PARALLELPERIOD

Exemplo:

```
CALCULATE(
    [Vendas],
    PARALLELPERIOD(
        Calendario[Data],
        -1,
        YEAR
    )
)
```

Também volta um ano.

Mas trabalha com **períodos completos**.

---

Exemplo:

Filtro:

```
Julho/2026
```

PARALLELPERIOD:

```
Julho/2025 inteiro
```

---

# Diferença principal

## SAMEPERIODLASTYEAR

"Mesmo intervalo de datas do ano passado"

Exemplo:

Filtro:

```
01/07/2026 até 15/07/2026
```

Retorna:

```
01/07/2025 até 15/07/2025
```

---

## PARALLELPERIOD

"Desloca o período inteiro"

Exemplo:

Filtro:

```
Julho/2026
```

Retorna:

```
Julho/2025
```

# Comparação simples

Imagine uma régua:

## SAMEPERIODLASTYEAR

Você pega:

```
15 centímetros da régua
```

e volta um ano:

```
mesmos 15 centímetros
```

---

## PARALLELPERIOD

Você fala:

```
Me dê o mês anterior
```

Ele entrega:

```
o mês inteiro
```

# A pegadinha da PL-300

A Microsoft gosta de comparar:

## SAMEPERIODLASTYEAR

Use quando quer:

> "Comparar exatamente o mesmo período do ano passado."

Exemplo:

- vendas de 15 dias de julho vs mesmos 15 dias de julho passado
- acumulado até hoje vs acumulado até mesma data ano passado

---

## PARALLELPERIOD

Use quando quer:

> "Mover um período completo."

Exemplo:

- mês anterior
- trimestre anterior
- ano anterior

---

# Regra para memorizar

|Função|Pense assim|
|---|---|
|SAMEPERIODLASTYEAR|"Mesmas datas do ano passado"|
|PARALLELPERIOD|"Outro período equivalente completo"|
|DATEADD|"Desloca as datas"|

