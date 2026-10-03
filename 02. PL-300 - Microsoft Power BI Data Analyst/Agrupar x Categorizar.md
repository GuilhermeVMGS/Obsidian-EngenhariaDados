
A diferença principal:

> **Agrupar cria novos grupos de dados manualmente. Categorizar informa ao Power BI o significado de uma coluna para melhorar a análise e visualização.**

---

# Agrupar (Group)

## O que é?

Agrupar é quando você **junta valores existentes em categorias criadas por você**.

Exemplo:

Você tem uma coluna:

### Produto

|Produto|
|---|
|Notebook|
|Mouse|
|Teclado|
|Monitor|

Você pode criar grupos:

```
Eletrônicos

    Notebook
    Monitor

Acessórios

    Mouse
    Teclado
```

O Power BI cria uma nova coluna:

|Produto|Grupo|
|---|---|
|Notebook|Eletrônicos|
|Monitor|Eletrônicos|
|Mouse|Acessórios|
|Teclado|Acessórios|

---

Outro exemplo:

Idade:

|Idade|
|---|
|18|
|25|
|40|
|65|

Você agrupa:

```
18-30
31-50
50+
```

---

## Quando usar?

Quando você quer criar uma análise específica.

Exemplo:

> "Quero analisar vendas por faixa de preço."

Você cria:

```
0-100
101-500
500+
```

---

# Categorizar (Categorize)

## O que é?

Categorizar é informar ao Power BI **que tipo de dado uma coluna representa**.

Exemplo:

Você tem:

|Cidade|
|---|
|Belo Horizonte|
|São Paulo|
|Rio de Janeiro|

O Power BI pode não saber que isso é uma localização.

Então você define:

```
Categoria de dados:
Cidade
```

Agora ele entende que pode usar:

- mapas;
- localização geográfica.

---

Exemplo:

Coluna:

```
Latitude
Longitude
```

Você define:

```
Categoria:
Latitude
Longitude
```

---

## Comparação:

||Agrupar|Categorizar|
|---|---|---|
|Objetivo|Criar grupos|Definir significado|
|Cria nova coluna?|✅ Sim|❌ Não|
|Feito pelo usuário?|✅ Sim|❌ Apenas classificação|
|Exemplo|Faixa etária|Cidade, CEP, URL|
|Uso principal|Análise|Visualização correta|