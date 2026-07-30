
# O que é Query Folding?

Query Folding é a capacidade do Power Query de **converter etapas M em comandos da origem dos dados**.

Ou seja:

Power Query:

```
M Language
    ↓
Query Folding
    ↓
SQL enviado para Synapse
```

A origem executa o trabalho pesado.

---

# Como saber se está funcionando?

No Power Query:

1. Abra o Editor do Power Query
2. Clique com botão direito em uma etapa
3. Veja:

**"Exibir consulta nativa"**

ou

**"View Native Query"**

Se estiver disponível:

✅ aquela etapa ainda está sendo enviada para a origem.

Se estiver desabilitado:

❌ o folding quebrou naquela etapa.

---

# Indicador de Query Folding

Nas versões mais recentes do Power BI existe o indicador:

- ✅ **Folding completo**
- ⚠️ **Folding parcial**
- ❌ **Sem folding**

Exemplo:

```
Fonte                    ✅
Filtro de data           ✅
Remover coluna           ✅
Coluna personalizada     ❌
```

A partir da coluna personalizada, o Power BI começa a processar localmente.