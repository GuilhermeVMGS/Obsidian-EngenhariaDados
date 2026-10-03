
## ISFILTERED

Verifica:

> Existe um filtro direto nesta coluna?

Exemplo:

Usuário clicou:

```
YTD
```

Resultado:

```
ISFILTERED(CalculationGroup[Item])
```

↓

TRUE

---

## ISCROSSFILTERED

Pergunta:

> Esta coluna está sendo filtrada direta **ou indiretamente**?

Isso inclui:

- filtros diretos
- filtros vindos de relacionamentos
- contexto de filtro

É mais abrangente.

## Por que a Microsoft prefere ISCROSSFILTERED?

Porque em Calculation Groups a seleção pode chegar por diferentes caminhos.

Então:

```
ISCROSSFILTERED(
CalculationGroup[Calculation Item]
)
```

é mais seguro.

---

## Pegadinha

Errado:

```
ISFILTERED(
CalculationGroup
)
```

Não existe.

Essas funções recebem:

✅ coluna

Não tabela.