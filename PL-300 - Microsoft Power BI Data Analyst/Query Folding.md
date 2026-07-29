
Query Folding é quando o Power Query envia transformações para o banco.

Exemplo:

Power Query:

```
Filtro Data > 2025
```

vira SQL:

```
SELECT *
FROM tabela
WHERE Data > '2025'
```

Isso é bom.

Desativar faz o Power Query trazer mais dados para o Power BI.

Pioraria o desempenho.