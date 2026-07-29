
![[Pasted image 20260729165740.png]]

### O que a prova cobra sobre isso:

1. **Identificar o gargalo:**
* Se o tempo de **DAX Query** for alto: O problema está na medida DAX mal otimizada ou na modelagem do banco.
   - Se o tempo de **Visual Display** for alto: O problema é o excesso de elementos gráficos no visual, muitos pontos de dados ou a capacidade da GPU/Navegador.
- Se o tempo de **DirectQuery** for alto: A fonte de dados externa (SQL Server, Oracle, etc.) está demorando para responder à consulta.

 2. **Exportar dados:** É possível exportar os resultados para um arquivo **.json**.

3. **Fluxo de Trabalho de Otimização:** Você clica em _Iniciar Gravação_ -> _Atualizar visuais_ -> Copiar a consulta do visual (_Copy query_) -> Colar no **DAX Studio** para rodar o `EVALUATE` e ver o plano de execução.