Existem três camadas:

1. Ordem Lógica (como o SQL "pensa")
2. Ordem física (como escrevemos)
3. Estrutura típica de um script

**Ordem Lógica de Execução do SQL (SELECT)**
Quando escrevemos algo como:

	SELECT colunas
	FROM tabela
	WHERE condição
	GROUP BY colunas
	HAVING condição
	ORDER BY colunas
	
O banco não executo nessa ordem. Na verdade, a ordem lógica de execução real é:

*FROM:* define a origem dos dados (tabelas, joins, subqueries)
*ON:* condições de JOIN
*JOIN:* combina as tabelas
*WHERE:* filtra as linhas (antes de agrupar)
*GROUP BY:* agrupa os dados
*HAVING:* filtra grupos
*SELECT:* escolhe colunas e calcula expressões
*DISTINCT:* remove duplicados
*ORDER BY:* ordena o resultado
*TOP / OFFSET / FETCH:* limita as linhas (a depender do SGBD)

***Exemplo***: porque o código abaixo da erro?

	SELECT SUM(vendas) AS total
	FROM pedidos
	WHERE total > 1000; -- ❌ ERRO

Porque *WHERE* acontece antes do *SELECT*, logo o total ainda não existe. Então o correto seria:

	SELECT SUM(vendas) AS total
	FROM pedidos
	HAVING SUM(vendas) > 1000;

Mesmo com o *HAVING* ocorrendo também após o *SELECT* o código funciona pois ele não depende do *SELECT* mas sim do *GROUP BY*, logo, as linhas já foram agregadas e suas funções já podem ser calculadas. Ou seja, o resultado do agrupamento já existe antes do *SELECT*.

**Ordem Física:**

Apesar da execução lógica ser diferente, a escrita segue uma convenção que facilita a legibilidade, manutenção e debug:

	SELECT
	FROM
	JOIN / ON
	WHERE
	GROUP BY
	HAVING
	ORDER BY


