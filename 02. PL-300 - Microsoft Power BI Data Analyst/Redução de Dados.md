
## O que é?

Redução de dados significa:

> Diminuir a quantidade de dados processados ou exibidos por um visual.

Isso melhora:

- Desempenho
- Tempo de carregamento
- Experiência do usuário

---

## Exemplo:

Você tem uma tabela:

```
Vendas
10 milhões de linhas
```

Você cria um gráfico:

```
Vendas por Produto
```

Existem:

```
50.000 produtos
```

Mostrar 50 mil barras seria pesado.

Então você usa:

- Top N
- Filtros
- Agregações

---

# Agregações

É uma forma de reduzir dados resumindo valores.

Exemplo:

Dados originais:

|Data|Loja|Venda|
|---|---|---|
|01/01|A|100|
|01/01|A|200|
|01/01|B|300|

Ao invés de carregar tudo:

```
3 linhas
```

Você cria:

|Loja|Total|
|---|---|
|A|300|
|B|300|

Agora o Power BI trabalha com menos dados.

## Outras formas de redução:

### 1. Top N

Mostrar somente:

```
Top 10 produtos
```

em vez de:

```
50 mil produtos
```

---

### 2. Filtrar dados

Exemplo:

Antes:

```
Vendas desde 2000
```

Depois:

```
Últimos 24 meses
```

---

### 3. Agregações

Criar tabelas resumidas:

```
Fato_Vendas_Detalhada

100 milhões linhas
```

↓

```
Fato_Vendas_Agregada

500 mil linhas
```

---

Para PL-300:

> "Qual técnica melhora desempenho reduzindo dados?"

Resposta:

✅ Agregações  
✅ Filtros  
✅ Top N