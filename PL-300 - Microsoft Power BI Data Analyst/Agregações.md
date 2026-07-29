
Agregações são uma técnica de otimização de desempenho usada para acelerar consultas em modelos com **volumes massivos de dados** (centenas de milhões ou bilhões de linhas).

### Como funciona na prática?

Em vez de fazer o Power BI processar e somar linha por linha de uma tabela fato gigantesca com dados no menor nível de detalhe (granulada), você cria uma **tabela resumida/agrupada (agregada)** em um nível mais alto.

#### Exemplo do mundo real:

- **Tabela Fato Detalhada (`fVendas`):** Contém 100 milhões de linhas com cada transação de caixa, com hora, minuto, produto e cliente.
- **Tabela Agregada (`fVendas_Agregada`):** Contém apenas o total de vendas agrupado por **Data, Categoria e Região** (cerca de 50.000 linhas).

Quando o usuário final abre o relatório e olha um gráfico de _Vendas por Mês e Região_, o Power BI é inteligente: ele **desvia a consulta automaticamente para a tabela agregada** (muito mais leve e rápida). Se o usuário resolver fazer um _drill-down_ para ver a transação exata de um minuto específico, aí sim o Power BI consulta a tabela detalhada.

![[Pasted image 20260729180543.png]]

