# 1. Transpor (Transpose)

**Transpor troca linhas por colunas e colunas por linhas.**

É como girar a tabela 90 graus.

## Antes:

|Campo|Valor|
|---|---|
|Produto|Notebook|
|Preço|5000|
|Estoque|10|

Depois de **Transpor**:

|Produto|Preço|Estoque|
|---|---|---|
|Notebook|5000|10|

A primeira linha vira cabeçalho (se você promover cabeçalhos depois).

---

## Quando usar?

Quando a fonte vem "deitada" ou "virada".

Exemplo de Excel mal estruturado:

||Jan|Fev|Mar|
|---|---|---|---|
|Vendas|100|200|300|

Você pode transpor para reorganizar.

---

# 2. Dinamizar coluna (Pivot Column)

Transforma **valores de uma coluna em nomes de colunas**.

Antes:

|Produto|Ano|Valor|
|---|---|---|
|A|2024|100|
|A|2025|200|

Depois:

|Produto|2024|2025|
|---|---|---|
|A|100|200|

Fluxo:

```
Linhas → Colunas
```

---

# 3. Anular dinamização (Unpivot)

É o contrário.

Transforma colunas em linhas.

Antes:

|Produto|2024|2025|
|---|---|---|
|A|100|200|

Depois:

|Produto|Ano|Valor|
|---|---|---|
|A|2024|100|
|A|2025|200|

Fluxo:

```
Colunas → Linhas
```

É uma das mais importantes para modelagem.