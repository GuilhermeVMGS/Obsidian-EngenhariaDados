
# O que é o Copilot?

O Copilot é um recurso de IA generativa integrado ao Power BI que ajuda a:

- Criar relatórios
- Gerar medidas DAX
- Resumir dados
- Explicar tendências
- Criar narrativas
- Fazer perguntas em linguagem natural

Em vez de escrever tudo manualmente, você pode pedir:

> "Crie uma medida de vendas acumuladas no ano."

Ou:

> "Resuma os principais motivos da queda das vendas."

---

# Onde o Copilot pode ser usado?

O Copilot não existe em apenas um lugar.

Ele aparece em vários pontos do Power BI.

## 1. Power BI Desktop

Auxilia durante a criação do relatório.

Pode:

- sugerir páginas;
- sugerir visuais;
- escrever medidas DAX;
- explicar medidas existentes;
- gerar resumos.

Exemplo:

Você importa uma tabela:

```
Vendas

Data
Produto
Estado
Valor
Quantidade
```

Você digita:

> "Crie um relatório mostrando vendas por estado."

O Copilot pode montar a página automaticamente.

---

## 2. Power BI Service

No Service ele ajuda a:

- criar relatórios;
- gerar insights;
- responder perguntas;
- criar narrativas.

---

## 3. Visual Narrativo (Narrative Visual)

É um visual especial.

Ele analisa os dados do relatório e escreve um texto automaticamente.

Exemplo:

Você possui:

|Região|Vendas|
|---|---|
|Sul|500 mil|
|Sudeste|800 mil|
|Norte|200 mil|

O Copilot escreve:

> "A região Sudeste apresentou o maior volume de vendas, representando aproximadamente 53% do total."

---

Você também pode orientar a resposta.

Exemplo:

> Resuma em tópicos.

Resultado:

- Sudeste lidera as vendas
- Sul é o segundo colocado
- Norte possui menor faturamento

Foi exatamente a questão que você enviou.

---

# 4. Chat com os dados

Uma funcionalidade muito interessante.

Você pergunta:

> Qual estado vendeu mais em junho?

Ele responde.

Outra:

> Mostre somente produtos acima de R$ 100 mil.

Ele pode alterar o relatório.

---

# 5. Geração de DAX

Você pode pedir:

> Crie uma medida de ticket médio.

O Copilot gera algo como:

```
Ticket Médio =
DIVIDE(
    SUM(Vendas[Valor]),
    COUNTROWS(Vendas)
)
```

Também explica medidas.

Exemplo:

Você seleciona:

```
Total =
SUM(Vendas[Valor])
```

Pergunta:

> Explique essa medida.

O Copilot responde.

---

# 6. Resumo de páginas

Imagine um dashboard enorme.

Você pergunta:

> Faça um resumo executivo.

Ele gera algo como:

- Receita cresceu 12%
- Lucro caiu 5%
- Região Sul apresentou melhor desempenho

---

# O que o Copilot NÃO faz?

Essa parte cai bastante.

Ele não:

❌ cria relacionamento automaticamente no modelo

❌ altera a fonte de dados

❌ cria ETL

❌ substitui Power Query

❌ muda permissões

❌ publica datasets

❌ configura Gateway

Ele auxilia na análise, não administra o ambiente.

---

# O que controla o formato da resposta?

Essa foi exatamente uma questão da sua prova.

Você quer:

Texto:

```
As vendas cresceram...
```

Ou:

Lista:

- Vendas cresceram
- Lucro aumentou

Ou:

Tabela.

Quem controla isso?

O prompt.

Exemplo:

> Responda usando bullet points.

ou

> Faça uma tabela.

ou

> Resuma em cinco linhas.

Não existe uma opção:

```
Formato

↓

Bullet Points
```

---

# Pré-requisitos

Aqui começam as pegadinhas.

Para usar Copilot normalmente é necessário:

## 1. Workspace em capacidade compatível

Normalmente:

- Microsoft Fabric Capacity
- Power BI Premium Capacity (quando suportado no cenário)

---

## 2. Administrador habilitar o Copilot

No Admin Portal.

Se estiver desabilitado:

Não aparece.

---

## 3. Tenant permitir IA

O administrador pode bloquear.

---

# Segurança

O Copilot respeita:

- RLS
- OLS
- Permissões do usuário

Exemplo:

Carlos só pode ver MG.

Se perguntar:

> Qual estado vendeu mais?

O Copilot responde usando apenas MG.

Ele nunca ignora a segurança.

---

# Prompt Engineering

Esse conceito aparece bastante.

Prompt é simplesmente a instrução enviada.

Exemplos ruins:

```
Explique.
```

Exemplos melhores:

```
Explique em até cinco tópicos.
```

ou

```
Compare 2024 e 2025.
```

ou

```
Use linguagem executiva.
```

Quanto melhor o prompt, melhor a resposta.

---

# O que ele consegue gerar?

Ele pode gerar:

✅ Medidas DAX

✅ Resumos

✅ Insights

✅ Narrativas

✅ Explicações

✅ Relatórios

✅ Visuais

---

Ele normalmente não gera:

❌ Power Query M complexo

❌ Pipelines

❌ Modelagem completa

❌ Gateway

---

# Questões que costumam cair

## "Como alterar o formato do texto?"

Resposta:

**Mudando o prompt.**

---

## "Copilot ignora RLS?"

Resposta:

Não.

---

## "Copilot cria relacionamentos automaticamente?"

Resposta:

Não.

---

## "Copilot pode gerar DAX?"

Resposta:

Sim.

---

## "Copilot pode explicar medidas?"

Resposta:

Sim.

---

## "Copilot pode resumir uma página?"

Resposta:

Sim.

---

# Comparação

|Recurso|Copilot consegue?|
|---|---|
|Criar medidas DAX|✅|
|Explicar medidas|✅|
|Criar relatório|✅|
|Gerar narrativa|✅|
|Resumir página|✅|
|Responder perguntas|✅|
|Alterar permissões|❌|
|Configurar Gateway|❌|
|Criar relacionamentos automaticamente|❌|
|Ignorar RLS|❌|