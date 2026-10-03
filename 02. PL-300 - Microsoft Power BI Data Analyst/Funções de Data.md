### `DATESMTD` (Time Intelligence)

- **O que faz:** Retorna uma tabela de datas do primeiro dia do mês até o dia atual no contexto.

- **Exemplo:** Se a sua visualização está mostrando a data de **15 de Março de 2026**, a `DATESMTD` gera internamente uma lista contendo as datas de **01/03/2026 até 15/03/2026**.

![[Pasted image 20260729165221.png]]
_Nota:_ Existem equivalentes para Trimestre (`DATESQTD`) e Ano (`DATESYTD`).

### `DATEADD` (Deslocamento Temporal)

- **O que faz:** Desloca o período selecionado para o futuro ou para o passado por um determinado intervalo.

- **Sintaxe:** `DATEADD(Datas, Quantidade, Intervalo)` onde o intervalo pode ser `DAY`, `MONTH`, `QUARTER` ou `YEAR`.
![[Pasted image 20260729165257.png]]
