![[Pasted image 20260729165500.png]]

- **OLTP / Dados Normalizados (Bancos de Origem):**
- Focado em não repetir dados. Dividido em dezenas de tabelas pequenas conectadas.
- _Exemplo:_ A tabela de `Clientes` se conecta à tabela de `Cidades`, que se conecta à tabela de `Estados`.

- **Esquema em Estrela / Star Schema (Ideal para o Power BI):**
- O engine do Power BI (VertiPaq) foi construído para lidar com **poucas tabelas com muitas linhas** e relacionamentos simples.
- **Tabela Fato (Centro):** Contém os números/métricas (vendas, quantidade, custos) e chaves estrangeiras. Costuma ter muitos registros e crescer rápido.
- **Tabelas Dimensão (Pontas da estrela):** Contêm o contexto do negócio (quem, onde, quando, o quê). Têm pouca variação e contêm chaves únicas (1 para Muitos com a Fato).

- **Snowflake (Floco de Neve):**

- Quando uma Dimensão se conecta a outra Dimensão antes de chegar na Fato (ex.: `fVendas` -> `dProduto` -> `dCategoria`).
- **Dica de Prova:** Na PL-300, a recomendação correta é quase sempre **mesclar (Merge)** essas tabelas no Power Query para achatar o modelo e transformá-lo em um **Star Schema**.