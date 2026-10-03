
![[Pasted image 20260729165740.png]]

## O que significa "Recuperação de Dados"?

Quando um visual é carregado, o Power BI precisa buscar dados.

A **recuperação de dados** é justamente o tempo que o Power BI leva para **buscar/calcular os dados necessários para aquele visual**.

Exemplo:

Você tem um gráfico:

```
Vendas por Estado
```

O Power BI gera uma consulta DAX parecida com:

```
SUM(Vendas[Valor])
```

Ele envia essa consulta para o mecanismo interno.

O tempo gasto nisso é a:

> **Recuperação de dados (Data Retrieval)**

---

## Exemplo no Performance Analyzer

Você clica:

```
Iniciar gravação
        ↓
Atualizar visual
```

Resultado:

|Item|Tempo|
|---|---|
|DAX Query|500 ms|
|Visual Display|200 ms|
|Other|50 ms|

### DAX Query alto:

Problema provavelmente:

- Medida DAX complexa
- Muitos filtros
- Modelo mal estruturado

---

### Visual Display alto:

Problema provavelmente:

- Visual muito pesado
- Muitos pontos no gráfico
- Muitos elementos visuais

---
### O que a prova cobra sobre isso:

1. **Identificar o gargalo:**
* Se o tempo de **DAX Query** for alto: O problema está na medida DAX mal otimizada ou na modelagem do banco.
   - Se o tempo de **Visual Display** for alto: O problema é o excesso de elementos gráficos no visual, muitos pontos de dados ou a capacidade da GPU/Navegador.
- Se o tempo de **DirectQuery** for alto: A fonte de dados externa (SQL Server, Oracle, etc.) está demorando para responder à consulta.

 2. **Exportar dados:** É possível exportar os resultados para um arquivo **.json**.

3. **Fluxo de Trabalho de Otimização:** Você clica em _Iniciar Gravação_ -> _Atualizar visuais_ -> Copiar a consulta do visual (_Copy query_) -> Colar no **DAX Studio** para rodar o `EVALUATE` e ver o plano de execução.

