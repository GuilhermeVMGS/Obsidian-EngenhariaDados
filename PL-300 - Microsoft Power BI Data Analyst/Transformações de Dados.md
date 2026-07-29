
# 1. Pivot Column (Coluna Dinâmica)

Transforma **valores de uma coluna em novas colunas**.
### Antes

| Produto | Mês | Vendas |
| ------- | --- | ------ |
| A       | Jan | 10     |
| A       | Fev | 15     |
| B       | Jan | 20     |
| B       | Fev | 30     |

↓

### Depois

| Produto | Jan | Fev |
| ------- | --- | --- |
| A       | 10  | 15  |
| B       | 20  | 30  |

O que aconteceu?

Os valores da coluna **Mês** viraram colunas.

### Quando usar

Quando deseja transformar categorias em colunas.

Exemplo:

- Meses
- Estados
- Tipos de pagamento
- Sexo

---

# 2. Unpivot Columns (Anular dinamização)

É exatamente o contrário.

Transforma **várias colunas em linhas**.

### Antes

|Produto|Jan|Fev|Mar|
|---|---|---|---|
|A|10|15|20|

↓

### Depois

|Produto|Mês|Vendas|
|---|---|---|
|A|Jan|10|
|A|Fev|15|
|A|Mar|20|

Agora existe apenas uma coluna chamada Mês.

---

## Quando usar

É uma das transformações mais importantes.

Sempre que os dados vierem "largos".

Exemplos:

- Um mês em cada coluna
- Um ano em cada coluna
- Uma filial em cada coluna

O Power BI prefere dados assim:

| Produto | Mês | Valor |

e não

| Produto | Jan | Fev | Mar |

---

# 3. Pivot x Unpivot

|Pivot|Unpivot|
|---|---|
|Linhas → Colunas|Colunas → Linhas|
|Cria mais colunas|Cria mais linhas|
|Dados ficam mais largos|Dados ficam mais altos|

---

# 4. Split Column (Dividir coluna)

Divide uma coluna.

### Antes

```
João Silva
```

↓

Dividir por espaço

|Nome|Sobrenome|
|---|---|
|João|Silva|

Pode dividir por:

- espaço
- vírgula
- hífen
- quantidade de caracteres
- posição

---

# 5. Merge Columns (Mesclar colunas)

Faz o contrário.

### Antes

|Nome|Sobrenome|
|---|---|
|João|Silva|

↓

|Nome Completo|
|---|
|João Silva|

---

# 6. Merge Queries (Mesclar consultas)

Não confunda!

**Merge Columns** junta colunas.

**Merge Queries** junta tabelas.

É equivalente ao SQL:

```
JOIN
```

Exemplo

Clientes

|ID|Nome|
|---|---|
|1|João|

Pedidos

|ClienteID|Valor|
|---|---|
|1|100|

↓

Após Merge

|ID|Nome|Valor|
|---|---|---|
|1|João|100|

---

# 7. Append Queries (Acrescentar)

É o equivalente ao

```
UNION ALL
```

ou

```
UNION
```

(no SQL sem remover duplicados)

Tabela A

|Nome|
|---|
|João|

Tabela B

|Nome|
|---|
|Maria|

↓

|Nome|
|---|
|João|
|Maria|

Empilha registros.

---

# 8. Group By (Agrupar)

Agrupa linhas.

Antes

|Produto|Venda|
|---|---|
|A|10|
|A|20|
|B|5|

↓

Agrupando por Produto

|Produto|Total|
|---|---|
|A|30|
|B|5|

Pode calcular:

- Soma
- Média
- Contagem
- Mínimo
- Máximo

---

# 9. Fill Down

Preenche valores para baixo.

Antes

|Categoria|
|---|
|Bebidas|
|null|
|null|

↓

|Categoria|
|---|
|Bebidas|
|Bebidas|
|Bebidas|

Muito usado em planilhas.

---

# 10. Fill Up

O contrário.

Preenche para cima.

---

# 11. Replace Values

Troca valores.

Exemplo

```
SP
```

↓

```
São Paulo
```

---

# 12. Remove Rows

Pode remover:

- primeiras linhas
- últimas linhas
- linhas vazias
- linhas duplicadas
- linhas com erro

---

# 13. Remove Duplicates

Mantém apenas uma ocorrência.

Antes

```
1
1
2
2
3
```

↓

```
1
2
3
```

---

# 14. Keep Rows

Mantém apenas:

- Top N
- Bottom N
- Intervalo
- Alternadas

---

# 15. Change Type

Talvez a transformação mais importante.

Converte para:

- Texto
- Número inteiro
- Decimal
- Data
- Data/Hora
- Lógico

---

# 16. Detect Data Type

O Power Query tenta descobrir automaticamente o tipo.

---

# 17. Transpose

Troca linhas por colunas.

Antes

|A|
|---|
|1|
|2|

↓

|1|2|

---

# 18. Reverse Rows

Inverte a ordem.

```
A
B
C
```

↓

```
C
B
A
```

---

# 19. Sort

Ordena.

- Crescente
- Decrescente

---

# 20. Filter

Mantém apenas linhas desejadas.

Exemplo

```
Valor > 100
```

---

# 21. Extract

Extrai parte do texto.

Exemplo

```
ABC123
```

↓

Primeiros 3 caracteres

```
ABC
```

Também pode extrair:

- últimos caracteres
- intervalo
- antes do delimitador
- depois do delimitador

---

# 22. Format

Transformações de texto.

Exemplo

```
joÃO
```

↓

```
João
```

Também:

- Maiúsculas
- Minúsculas
- Capitalizar
- Remover espaços
- Limpar caracteres invisíveis

---

# 23. Add Column

Cria novas colunas.

Pode usar:

- Soma
- Data
- Hora
- Texto
- Condicional
- Índice

---

# 24. Conditional Column

Cria um IF sem escrever M.

Exemplo

```
Se Valor > 100
Alta

Senão

Baixa
```

---

# 25. Custom Column

Permite escrever fórmulas em **linguagem M**.

Exemplo

```
[Preço] * [Quantidade]
```

---

# 26. Index Column

Cria uma numeração.

```
1
2
3
4
```

Muito usada para ordenação.

---

# 27. Duplicate Column

Cria uma cópia.

---

# 28. Reference Query

Cria uma nova consulta baseada em outra.

As alterações na consulta original podem refletir na nova.

---

# 29. Duplicate Query

Cria uma cópia independente da consulta.