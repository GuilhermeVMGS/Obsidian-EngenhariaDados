
Esse é um dos assuntos mais importantes da PL-300.

Vamos entender primeiro como um modelo funciona.

Imagine:

```
Clientes

Pedidos

Produtos
```

Cada uma é uma tabela.

Dentro delas existem colunas.

---

## Coluna Calculada

Uma coluna calculada cria **uma nova coluna física**.

Exemplo:

Tabela:

|Nascimento|
|---|
|1995|
|2000|

Você cria:

```
Idade =
YEAR(TODAY()) - Clientes[Nascimento]
```

Resultado:

|Nascimento|Idade|
|---|---|
|1995|31|
|2000|26|

A coluna passa a existir no modelo.

Ela é armazenada.

Ela ocupa memória.

Ela é calculada durante o refresh.

---

### Características

✅ É armazenada.

✅ Pode participar de relacionamentos.

✅ Pode ser usada em segmentações.

✅ Pode ser usada em eixos.

---

## Medida

Agora imagine:

Você quer:

```
Total de vendas
```

Isso não faz sentido virar uma coluna.

Você quer apenas um número.

Então cria:

```
Total =
SUM(Vendas[Valor])
```

Ela não cria coluna.

Ela não ocupa espaço armazenando resultados.

Ela é calculada **quando o usuário abre o relatório**.

---

### Características

Não é armazenada.

Depende do contexto.

Calculada sob demanda.

Ideal para agregações.

---

## Tabela Calculada

Agora imagine:

Você deseja criar uma nova tabela.

```
ResumoProdutos =
SUMMARIZE(...)
```

Ela cria:

```
Clientes

Pedidos

Produtos

ResumoProdutos
```

Agora existe uma nova tabela.

Ela também é armazenada.

---

## Relacionamentos

É aqui que entra a questão.

---

### Coluna Calculada

Ela não cria um relacionamento.

Mas ela pode servir como chave.

Exemplo:

```
Clientes

CPF
```

Você cria:

```
CPFFormatado
```

Depois cria:

```
Clientes[CPFFormatado]

↓

Pedidos[CPF]
```

Ou seja:

A coluna participa do relacionamento da tabela.

---

### Tabela Calculada

Como ela virou uma tabela nova:

```
Resumo

↓

Clientes

↓

Produtos
```

Ela pode criar relacionamentos normalmente.

---

Por isso a Microsoft respondeu:

> As tabelas calculadas podem estabelecer relações com outras tabelas, enquanto as colunas calculadas tornam-se parte das relações existentes da tabela pai.