## Duplicar (Duplicate)

Cria uma **cópia independente**.

```
Clientes
   │
   └── Duplicar
         │
         └── Clientes (2)
```

Depois da duplicação:

- alterações na cópia não afetam a original;
- alterações futuras na original também não alteram a cópia.

Use quando quiser duas consultas totalmente separadas.

---

## Referência (Reference)

Cria uma consulta baseada na saída da outra.

```
Clientes
     │
     └── Referência
            │
            └── Clientes Ativos
```

A consulta "Clientes Ativos" começa exatamente onde "Clientes" terminou.

Se a consulta original receber um novo passo, a referência também enxergará essa mudança.

Muito usado para evitar repetir importações.

### PL-300

**Duplicate = cópia independente**

**Reference = depende da consulta original**