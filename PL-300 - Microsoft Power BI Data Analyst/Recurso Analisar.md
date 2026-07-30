
# O que é o recurso **Analisar** no Power BI?

O **Analisar** permite clicar em um ponto de dado de um visual e pedir que o Power BI explique aquele valor.

Exemplo:

Você tem um gráfico:

```
Vendas por semana

Semana 1  ███████
Semana 2  █████████
Semana 3  █████████████████  ← muito alta
Semana 4  ████████
```

O gerente pergunta:

> "Por que a Semana 3 teve vendas tão altas?"

Você clica:

```
Botão direito na barra
        ↓
Analisar
        ↓
Explicar o aumento
```

O Power BI procura padrões nos dados e gera explicações.

---

# Que tipo de resultado ele fornece?

Ele pode mostrar:

## 1. Principais fatores que influenciaram o aumento

Exemplo:

> "As vendas aumentaram principalmente na região Sul devido ao crescimento do produto Morango."

Ele tenta encontrar:

- categorias relacionadas
- regiões
- produtos
- períodos
- segmentos

que explicam a mudança.

---

## 2. Comparações relevantes

Exemplo:

> "As vendas foram 35% maiores que a média das últimas 12 semanas."

---

## 3. Anomalias ou tendências

Exemplo:

> "Essa semana apresentou um valor fora do padrão histórico."

---

# Como funciona por trás?

O Power BI analisa:

- medidas
- dimensões
- filtros aplicados
- histórico dos dados

Ele procura:

"Quais campos têm maior relação com essa variação?"

Exemplo:

Você selecionou:

```
Região: Sudeste
Semana: 30
Produto: Frutas
```

O Power BI pode descobrir:

```
Aumento explicado por:

+40% Morango
+25% Banana
+15% Região Centro
```

---

# Atenção para a PL-300

Esse recurso depende de um **modelo semântico bem estruturado**.

Ele funciona melhor quando você tem:

✅ relacionamentos corretos  
✅ medidas bem definidas  
✅ nomes claros  
✅ dados históricos suficientes

---

# Existem outros recursos parecidos?

Sim. A Microsoft possui vários recursos de análise automática.

---

# 1. Analisar → Explicar o aumento/diminuição

Esse é o da questão.

Uso:

> "Por que esse valor aumentou?"

Exemplo:

Botão direito:

```
Analisar
 ├── Explicar o aumento
 └── Explicar a diminuição
```

---

# 2. Q&A (Perguntas e Respostas)

Permite perguntar usando linguagem natural.

Exemplo:

Você escreve:

> "Qual foi a venda por região em 2026?"

O Power BI tenta criar um visual.

Ele usa:

- modelo semântico
- nomes de tabelas
- medidas
- sinônimos

---

# 3. Copilot no Power BI

Mais recente.

Permite:

- resumir relatórios
- gerar narrativas
- criar páginas
- explicar dados

Exemplo:

> "Resuma os principais pontos desse relatório."

Ele gera texto.

---

# 4. Insights rápidos (Quick Insights)

Também é um recurso de IA.

Ele analisa um conjunto de dados procurando:

- tendências
- correlações
- outliers
- sazonalidade

Exemplo:

> "As vendas aumentaram nos finais de semana."

---

# 5. Smart Narrative (Narrativa Inteligente)

Cria textos automaticamente a partir dos visuais.

Exemplo:

Visual:

```
Vendas: R$ 5 milhões
Crescimento: +15%
```

Narrativa:

> "As vendas cresceram 15% comparadas ao período anterior."

---

# Comparação para PL-300

| Recurso             | Para que serve                         |
| ------------------- | -------------------------------------- |
| **Analisar**        | Explicar um ponto específico do visual |
| **Q&A**             | Fazer perguntas em linguagem natural   |
| **Copilot**         | Gerar análises, textos e conteúdo      |
| **Quick Insights**  | Encontrar padrões automaticamente      |
| **Smart Narrative** | Criar explicações textuais dos dados   |