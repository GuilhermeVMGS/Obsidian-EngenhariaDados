Primeiro:

Alerta NÃO funciona no relatório.

Funciona em: **dashboard (painéis)**.

Mais especificamente: nos **tiles** fixados.

## Alerta (Alert)

Dispara quando um valor atingir determinada condição.

Exemplo

```
Receita

< 50.000
```

↓

Recebe um aviso.

Só funciona em determinados Tiles (como Cartão, KPI e Medidor).

---

## Assinatura (Subscription)

Envia o relatório periodicamente.

Exemplo

Toda segunda-feira

08:00

↓

Recebe um e-mail com o relatório.

Não depende de condições.

---

Resumo

| Alerta              | Assinatura        |
| ------------------- | ----------------- |
| Baseado em condição | Baseado em agenda |
| Valor mudou         | Horário definido  |
| Notificação         | E-mail            |

## Posso usar uma única assinatura para vários cronogramas?

Não.

Cada assinatura possui apenas **um cronograma**.

Ela pode enviar para vários destinatários.

Mas todos recebem naquele mesmo horário.

Exemplo:

Assinatura:

```
Segunda

08:00
```

Pode enviar para:

```
João

Maria

Pedro
```

Todos recebem segunda às 08h.

---

Agora imagine:

João:

Segunda.

Maria:

Quarta.

Pedro:

Sexta.

Uma assinatura não consegue fazer isso.

---

Por isso:

É necessário criar:

```
Assinatura 1

↓

Segunda

Grupo A
```

---

```
Assinatura 2

↓

Quarta

Grupo B
```

---

```
Assinatura 3

↓

Sexta

Grupo C
```

---

## Assinatura NÃO é agendamento de refresh.

São recursos diferentes.

Refresh:

Atualiza dados.

---

Subscription:

Envia relatório.