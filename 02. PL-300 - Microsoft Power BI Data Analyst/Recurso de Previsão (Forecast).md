
# O que é o recurso de Previsão (Forecast) no Power BI?

O **Forecast** usa modelos estatísticos para tentar prever valores futuros com base no histórico.

Exemplo:

Você tem vendas:

|Mês|Vendas|
|---|---|
|Jan/2025|100|
|Fev/2025|120|
|Mar/2025|130|
|Abr/2025|150|
|Mai/2025|160|

O Power BI analisa esse comportamento e cria uma previsão:

|Mês|Vendas|
|---|---|
|Jun/2025|170 (previsto)|
|Jul/2025|180 (previsto)|
|Ago/2025|190 (previsto)|

---

# Como ele aparece no gráfico?

Exemplo:

```
Vendas

200 |                         . . . . previsão
    |                      .´
150 |                  ●
    |             ●
100 |        ●
    |   ●
    |
    +--------------------------------
       Jan Fev Mar Abr Mai Jun Jul
```

Parte sólida:

➡️ dados reais

Parte pontilhada:

➡️ previsão

---

# Onde encontrar?

No Power BI Desktop:

1. Crie um gráfico de linhas
2. Vá em:

```
Painel Análises
        ↓
Previsão
        ↓
Adicionar
```

Você configura:

- comprimento da previsão
- intervalo de confiança
- sazonalidade
- nível de confiança

---

# Por que precisa de eixo contínuo?

Essa é a pegadinha da questão.

O Power BI precisa entender que existe uma **linha do tempo**.

Exemplo correto:

```
01/01/2025
02/01/2025
03/01/2025
04/01/2025
```

Ele entende:

"Existe sequência temporal."

---

Exemplo incorreto:

```
Janeiro
Março
Agosto
Produto A
Produto B
```

Isso é categoria, não tempo.

---

# Eixo contínuo x categórico

Isso cai bastante na PL-300.

## Eixo contínuo

Trata como uma escala:

```
Jan ---- Fev ---- Mar ---- Abr
```

Os pontos têm distância proporcional.

Usado para:

✅ previsão  
✅ tendências  
✅ séries temporais

---

## Eixo categórico

Trata como categorias separadas:

```
Jan | Fev | Mar | Abr
```

Cada item é independente.

Usado para:

- comparação entre categorias
- ranking
- distribuição