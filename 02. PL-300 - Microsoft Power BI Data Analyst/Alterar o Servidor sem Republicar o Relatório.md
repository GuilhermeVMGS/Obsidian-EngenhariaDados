
Passo a passo para trocar a fonte de dados (ex.: de um servidor de Desenvolvimento para Produção) diretamente no Power BI Service:

1. **No Power BI Desktop:**
    - Crie um parâmetro no Power Query para armazenar o endereço do servidor (ex.: `pServidor`).
    - Substitua a URL ou nome do servidor estático no código M pelo parâmetro criado.
    - Publique o relatório no Power BI Service.

2. **No Power BI Service:**
    - Acesse as **Configurações** do modelo semântico (dataset).
    - Abra a seção **Parâmetros**.
    - Altere o valor do parâmetro `pServidor` para o endereço do servidor de produção e salve.