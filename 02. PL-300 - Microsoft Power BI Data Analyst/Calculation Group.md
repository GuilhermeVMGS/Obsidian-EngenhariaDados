## O que é um Calculation Group?

Imagine que você tenha 30 medidas.

```
Vendas

Lucro

Quantidade

Margem

Custo
```

Agora quer mostrar cada uma delas:

- Ano Atual
- Ano Anterior
- Crescimento
- MTD
- YTD
- Rolling 12 meses

Sem Calculation Group:

```
30 medidas

×

6 cálculos

=

180 medidas
```

Muito trabalho.

---

Com Calculation Group:

Você cria apenas:

```
Ano Atual

Ano Anterior

YTD

MTD

Rolling

...
```

e qualquer medida pode usar esses cálculos.

---

## Como o usuário escolhe?

Normalmente existe um slicer:

```
Ano Atual

Ano Anterior

YTD

MTD
```

---

Agora imagine que o usuário não escolheu nada.

O Calculation Group precisa descobrir isso.