
O **Drill-through** permite navegar de uma página resumida para uma página de detalhes **levando o contexto do dado selecionado**.

Exemplo do cenário:

## Página principal:

Dashboard de ocupação:

|Hotel|Ocupação|
|---|---|
|Hotel A|85%|
|Hotel B|70%|

O usuário clica:

```
Hotel A
```

O Power BI abre:

## Página de detalhes:

Reservas do Hotel A:

|Hóspede|Check-in|Quarto|
|---|---|---|
|João|01/08|101|
|Maria|03/08|205|

O filtro:

```
Hotel = Hotel A
```

foi transportado automaticamente.

Esse é o conceito de **contexto de drill-through**.

---

# Onde configuramos isso?

Na página que será o destino do drill-through.

Ou seja:

Página:

```
Detalhes de Reservas
```

Você configura:

```
Painel Visualizações
        ↓
Campo Drill-through / Detalhes
        ↓
Arrastar campo
```

Exemplo:

Adicionar:

```
Hotel[NomeHotel]
```

na área de Drill-through.

---

Depois disso, essa página passa a aceitar:

```
Hotel A
```

como contexto recebido.