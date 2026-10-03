
## O que é?

Um **esquema plano** é uma estrutura de banco onde todas as informações ficam armazenadas em uma única tabela.

Ou seja:

> Dados de transações e informações descritivas ficam misturados no mesmo lugar.

---

## Exemplo

Uma tabela de vendas:

|Data|Cliente|Cidade|Produto|Categoria|Valor|
|---|---|---|---|---|---|
|01/01|João|BH|Notebook|Eletrônico|5000|
|02/01|Maria|SP|Mouse|Acessório|100|

Tudo está junto:

- Dados da venda
- Dados do cliente
- Dados do produto
- Dados geográficos

---

# Problemas do esquema plano

## 1. Duplicação de dados

Imagine:

|Cliente|Cidade|
|---|---|
|João|BH|
|João|BH|
|João|BH|

A informação do cliente fica repetida milhares de vezes.

---

## 2. Maior tamanho do modelo

Como existem muitos valores repetidos, o modelo pode ficar maior.

---

## 3. Menor desempenho

O Power BI precisa trabalhar com uma tabela grande e menos organizada.

---

## 4. Menor facilidade de manutenção

Se uma informação muda:

Exemplo:

```
Cliente João mudou de cidade
```

Você precisa atualizar várias linhas.

---

# Esquema Plano x Modelo Estrela

O Power BI recomenda o **modelo estrela**.

## Esquema plano:

```
Uma tabela gigante

Vendas
--------------------------------
Data
Cliente
Cidade
Produto
Categoria
Valor
```

---

## Modelo estrela:

```
              DimProduto
                   |
                   |
DimCliente ---- FatoVendas ---- DimData
                   |
                   |
              DimLoja
```

---

## No modelo estrela:

### Tabela fato:

Guarda eventos:

Exemplo:

```
FatoVendas

VendaID
ProdutoID
ClienteID
DataID
Valor
```

---

### Tabelas dimensão:

Guardam descrição:

```
DimProduto

ProdutoID
NomeProduto
Categoria
Marca
```

---

# Por que o modelo estrela é melhor?

Porque:

✅ Reduz redundância  
✅ Melhora desempenho  
✅ Facilita DAX  
✅ Facilita filtros e relacionamentos  
✅ É a prática recomendada no Power BI