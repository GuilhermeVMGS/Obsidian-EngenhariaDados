
Definido nas propriedades de cada tabela na exibição de modelo:

### 1. Importar (Import)

- Os dados são carregados para o modelo e armazenados em memória (VertiPaq).
- Oferece o melhor desempenho para consultas e cálculos DAX.
- Os dados só mudam após uma atualização (manual ou agendada).

### 2. DirectQuery

- Os dados não são armazenados na memória do Power BI.
- A cada interação no relatório, o Power BI traduz a necessidade em uma consulta nativa (ex.: SQL) e envia ao banco de origem.
- Recomendado para volumes massivos de dados ou quando a informação precisa estar em tempo real.

### 3. Duplo (Dual)

* A tabela pode ser utilizada tanto como **Import** quanto como **DirectQuery**, conforme a necessidade da consulta. O mecanismo do Power BI decide automaticamente qual modo utilizar para oferecer melhor desempenho.
- Utilizada principalmente em tabelas dimensão conectadas a tabelas fato em DirectQuery dentro de modelos compostos, permitindo que a engine escolha a forma mais rápida de responder à consulta.

![[Pasted image 20260729171722.png]]

Quando você se conecta a uma fonte de dados, normalmente as opções são:

- ✅ **Import**
- ✅ **DirectQuery**
- (em algumas fontes também pode haver **Conexão Dinâmica (Live Connection)**)

O **Dual** é definido **depois**, nas propriedades da tabela, e **somente em modelos compostos**, quando faz sentido.

O fluxo é assim:

1. **Obter Dados** → escolhe **Import** ou **DirectQuery**.
2. Carrega as tabelas.
3. Na **Exibição de Modelo**, seleciona uma tabela.
4. Em **Armazenamento (Storage mode)**, se as condições permitirem, altera de **Import** para **Dual**.

### Por que o Dual não aparece na conexão?

Porque **Dual não é um tipo de conexão com a fonte de dados**. Ele é um **modo de armazenamento da tabela dentro do modelo do Power BI**.

Na prática, o cenário mais comum é:

- Tabela **Fato Vendas** → DirectQuery
- Tabela **Dim Cliente** → Dual
- Tabela **Dim Produto** → Dual

Assim, quando uma consulta usa apenas dimensões, o Power BI pode responder pela cópia em memória. Quando precisa acessar a fato em DirectQuery, as dimensões se comportam como DirectQuery para manter a consistência.

Portanto, para a PL-300, a regra é simples:

- **Obter Dados:** Import ou DirectQuery.
- **Exibição de Modelo:** Import, DirectQuery ou Dual (quando suportado).