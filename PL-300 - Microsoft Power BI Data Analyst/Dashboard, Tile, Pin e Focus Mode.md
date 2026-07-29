# 1. Dashboard (Painel)

O **Dashboard** existe **somente no Power BI Service**.

É uma página única que pode reunir visuais de vários relatórios diferentes.

Exemplo:

```
Dashboard Executivo

📈 Receita (Relatório Financeiro)

📊 Clientes (Relatório CRM)

🗺️ Mapa (Relatório Comercial)

📉 Estoque (Relatório Logística)
```

Cada um desses elementos é um **Tile (Bloco)**.

---

# 2. Tile (Bloco)

Um **Tile** é um visual fixado em um Dashboard.

Ele pode vir de:

- um relatório
- outro dashboard
- uma imagem
- uma página da web
- um streaming dataset
- um Q&A

Ou seja:

**Visual ≠ Tile**

No relatório:

```
Gráfico de Barras
```

↓

Depois de "Fixar"

↓

No Dashboard

```
Tile
```

O Tile é apenas uma representação daquele visual.

---

# 3. Pin (Fixar)

"Pin" significa **copiar um visual para um Dashboard**.

Não move o visual.

Não cria outro relatório.

Apenas cria um Tile.

Exemplo:

Relatório

```
Gráfico de vendas
```

↓

Pin

↓

Dashboard

```
Tile de vendas
```

Se o relatório atualizar, o Tile também atualiza.

---

# 4. Focus Mode (Modo de Foco)

O Focus Mode serve para visualizar **um único Tile em tela maior**.

Imagine um Dashboard cheio.

Você clica em um Tile.

Agora ele ocupa praticamente toda a tela.

Isso é Focus Mode.

---

## O que pode fazer nele?

Além de ampliar o visual, você pode:

- exportar dados
- aplicar alguns filtros
- visualizar detalhes
- usar **View Insights**
- fixar (Pin) novos visuais gerados pelos Insights

---

# 5. View Insights (Ver Insights)

Esse recurso usa IA do Power BI.

Ele analisa automaticamente os dados daquele visual.

Exemplo

Você tem um gráfico:

```
Vendas por Estado
```

O Power BI pode descobrir automaticamente:

- Estado com maior crescimento
- Estado com maior queda
- Outliers
- Tendências
- Correlações

Ele gera novos gráficos automaticamente.

Você não precisou construir nada.

---

## Exemplo

Você tinha:

```
Treemap

Produtos
```

↓

View Insights

↓

Pode aparecer:

```
Linha temporal

Receita ao longo do tempo
```

ou

```
Gráfico de barras

Categorias responsáveis pela queda
```

São novos visuais criados automaticamente.

---

# 6. Get Insights (Obter Insights)

Muita gente confunde.

Existe o **Get Insights** em conjuntos de dados e relatórios.

Também utiliza IA.

A ideia é semelhante:

> "Analise meus dados automaticamente."

O Power BI procura:

- tendências
- anomalias
- correlações
- padrões

É uma análise automática.

---

## Diferença prática

**View Insights**

➡ normalmente parte de um visual específico.

**Get Insights**

➡ analisa um conjunto maior de dados.

Na prova, ambos estão relacionados à IA do Power BI.

---

# 7. Spotlight (Destaque)

Esse recurso não cria gráficos.

Ele apenas destaca um visual.

Imagine a página:

```
████████████

██ gráfico ██

████████████
```

Ao usar Spotlight:

```
Tela escurece

Só o gráfico fica iluminado
```

Serve para apresentações.

Não altera dados.

Não cria Tiles.

Não gera Insights.

---

# 8. Treemap (Mapa de árvore)

É aquele gráfico composto por retângulos.

Exemplo

```
███████
██A███
███████

████
██B█

███
C
```

Cada retângulo representa uma categoria.

O tamanho depende do valor.

Muito usado para mostrar participação.

Exemplo

Categorias

- Eletrônicos
- Vestuário
- Alimentos

Quanto maior a receita, maior o retângulo.

---

# 9. Fixar visuais gerados pelos Insights

Essa é uma funcionalidade importante.

Fluxo:

```
Tile

↓

Focus Mode

↓

View Insights

↓

Power BI cria gráficos

↓

Gostou de um?

↓

Pin

↓

Novo Tile no Dashboard
```

Não é preciso criar um relatório novo.

---

# Resumo dos conceitos

|Conceito|O que faz?|
|---|---|
|**Dashboard**|Página única composta por Tiles. Existe apenas no Power BI Service.|
|**Tile**|Visual fixado em um Dashboard.|
|**Pin**|Copia um visual para um Dashboard como um Tile.|
|**Focus Mode**|Amplia um Tile para análise detalhada.|
|**View Insights**|Usa IA para gerar automaticamente visuais relacionados ao Tile selecionado.|
|**Get Insights**|Usa IA para analisar um conjunto de dados ou relatório e identificar padrões e tendências.|
|**Spotlight**|Destaca um visual durante uma apresentação; não altera dados nem cria novos visuais.|
|**Treemap**|Gráfico de retângulos proporcionais, usado para mostrar participação de categorias em um total.|

### O que mais cai na PL-300

As pegadinhas mais frequentes são:

- **Dashboard** existe **apenas no Power BI Service**.
- **Pin** cria um **Tile**, não copia um relatório inteiro.
- **Focus Mode** apenas amplia um Tile para análise.
- **View Insights** pode gerar **novos visuais automaticamente** usando IA.
- **Spotlight** é apenas um destaque visual para apresentação; não faz análises nem cria novos objetos.