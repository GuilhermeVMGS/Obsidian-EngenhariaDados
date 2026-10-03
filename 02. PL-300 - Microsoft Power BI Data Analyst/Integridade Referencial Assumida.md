
É uma opção disponível **em relacionamentos de tabelas que utilizam DirectQuery**.

Ao habilitá-la, você está dizendo ao Power BI:

> **"Pode confiar que todas as chaves da tabela fato existem na tabela dimensão."**

Ou seja, **não existem registros órfãos**.

Exemplo:
![[Pasted image 20260729172353.png]]
![[Pasted image 20260729172409.png]]
# Por que o Power BI usa LEFT JOIN por padrão?

Como ele **não sabe** se existem registros órfãos, ele precisa garantir que nenhuma venda seja perdida.

Então gera algo parecido com:

```
SELECT ...
FROM FatoVendas F
LEFT JOIN DimProduto D
ON F.ProdutoID = D.ProdutoID
```

O **LEFT JOIN** mantém **todas** as vendas.

Mesmo que o produto não exista, a venda continua aparecendo.