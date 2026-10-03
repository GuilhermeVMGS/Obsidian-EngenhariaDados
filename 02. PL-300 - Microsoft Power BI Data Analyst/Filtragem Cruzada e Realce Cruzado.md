
A ideia principal:

> **Filtragem cruzada altera o contexto dos dados exibidos, removendo informações que não correspondem à seleção.  
> Realce cruzado mantém todos os dados visíveis, mas destaca apenas os dados relacionados à seleção.**

---

# Filtragem Cruzada (Cross-filtering)

## O que acontece?

Quando você seleciona um valor em um visual, os outros visuais são **filtrados** para mostrar apenas os dados relacionados.

Os valores que não fazem parte da seleção **desaparecem**.

---

## Exemplo

Você tem dois visuais:

### Gráfico de vendas por região:

|Região|Vendas|
|---|---|
|Sul|100.000|
|Sudeste|200.000|
|Norte|50.000|

### Tabela de produtos:

|Produto|Vendas|
|---|---|
|Notebook|100.000|
|Mouse|50.000|
|Teclado|200.000|

Você clica em:

```
Região = Sul
```

O Power BI aplica um filtro.

Resultado:

Tabela:

|Produto|Vendas|
|---|---|
|Notebook|100.000|

Os produtos sem vendas no Sul desaparecem.

---

Visualmente:

Antes:

```
Notebook ███████
Mouse    ███
Teclado  █████████
```

Depois:

```
Notebook ███████
```

---

## Quando usar?

Quando você quer responder:

> "Mostre somente os dados relacionados a essa seleção."

Exemplo:

"Quero ver apenas vendas da região Sul."

---

# Realce Cruzado (Cross-highlighting)

## O que acontece?

O Power BI mantém todos os dados visíveis, mas destaca a parte correspondente à seleção.

Os dados não relacionados continuam aparecendo como contexto.

---

## Exemplo

Mesmo gráfico:

Você seleciona:

```
Região = Sul
```

A tabela continua:

|Produto|Vendas|
|---|---|
|Notebook|100.000|
|Mouse|50.000|
|Teclado|200.000|

Mas o Power BI destaca apenas o que pertence ao Sul.

Visualmente:

```
Notebook ███████  ← selecionado

Mouse    ░░░
Teclado  ░░░░
```

---

## Quando usar?

Quando você quer comparar:

> "Qual é a participação dessa seleção em relação ao total?"

Exemplo:

"Quanto das vendas totais vieram da região Sul?"

---

# Comparação direta

||Filtragem Cruzada|Realce Cruzado|
|---|---|---|
|Remove dados?|✅ Sim|❌ Não|
|Mantém o total visível?|❌ Não|✅ Sim|
|Mostra contexto?|Menos|Mais|
|Uso principal|Filtrar análise|Comparar impacto|