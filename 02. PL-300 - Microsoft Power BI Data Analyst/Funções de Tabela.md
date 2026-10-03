
- **`DATATABLE`:**
   - **O que faz:** Cria uma tabela estática (hardcoded) inserindo os dados e tipos diretamente no código DAX.
   - **Uso:** Tabelas auxiliares pequenas (ex.: tabela de parâmetros simples). Não depende de outras tabelas do modelo.

![[Pasted image 20260729162140.png]]

- **`CALCULATETABLE`:**
   - **O que faz:** Avalia uma expressão de tabela em um contexto de filtro modificado. 
   - **Uso:** Equivalente ao `CALCULATE`, mas retorna uma tabela inteira filtrada em vez de um único valor escalar.
![[Pasted image 20260729162201.png]]
