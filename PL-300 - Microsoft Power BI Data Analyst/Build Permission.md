
## A melhor forma de pensar

Imagine que o modelo semântico é um banco de dados.

### Build

É como ter permissão de:

```
SELECT
```

Você faz consultas.

Você cria dashboards.

Você usa Excel.

Mas não altera a estrutura.

---

### Contributor

É como ter permissão de:

```
ALTER
CREATE
UPDATE
```

Você consegue modificar a estrutura do modelo (dentro do fluxo de edição/publicação do Power BI).

A tradução **"Build Permission" → "Permissão de Compilação"** não ajuda muito, porque "compilar" faz parecer que está compilando código, mas **não é isso**.

Pense em **Build** como:

> **"Permissão para construir algo novo usando este modelo semântico."**

Não significa editar o modelo, e sim **usar o modelo como base** para criar análises.

---

# O que é a Build Permission?

Imagine que você publicou um modelo semântico no Power BI Service.

```
Modelo Semântico

Vendas
Clientes
Produtos
Calendário
```

Agora existem vários usuários.

Cada um possui uma permissão diferente.

---

## Usuário 1 — Read (Leitura)

Ele pode:

✅ Abrir relatório

✅ Interagir com filtros

✅ Ver gráficos

Mas não pode:

❌ Criar um novo relatório usando aquele modelo

❌ Conectar o Excel

---

## Usuário 2 — Build

Ele pode tudo que o usuário de Read faz **e mais**:

✅ Criar um novo relatório usando o mesmo modelo

✅ Usar Analyze in Excel

✅ Conectar ferramentas externas (como Excel)

✅ Criar uma Tabela Dinâmica no Excel usando o modelo

---

## Usuário 3 — Write

Pode tudo isso e ainda:

✅ Editar o modelo

✅ Alterar dataset

✅ Publicar alterações

---

# Por que o nome "Build"?

Imagine uma casa.

O modelo semântico é a fundação.

```
           Relatório A

                ▲

Modelo Semântico

                ▼

           Relatório B
```

Quem possui Build pode construir novos relatórios em cima dessa fundação.

Quem possui apenas Read apenas entra na casa pronta.

---

# O exemplo do Excel

Essa é a questão clássica da PL-300.

O usuário quer:

```
Excel

↓

Inserir

↓

Tabela Dinâmica

↓

Power BI Dataset
```

O Excel precisa consultar diretamente o modelo.

Para isso ele precisa da permissão:

✅ Build

Sem ela:

```
Excel

↓

Permissão negada
```

Mesmo que ele consiga abrir o relatório no navegador.

---

# Outro exemplo

Você publicou:

```
Modelo

↓

Dashboard Financeiro
```

João possui apenas Read.

Ele consegue abrir.

Mas ele quer criar:

```
Meu Relatório de Vendas
```

usando aquele modelo.

Não consegue.

Falta:

Build.

---

# O que o Build NÃO permite?

Ele **não** permite:

❌ Alterar tabelas

❌ Criar relacionamentos

❌ Alterar medidas do modelo publicado

❌ Modificar Power Query

❌ Publicar uma nova versão do dataset

Essas ações exigem permissões de edição (Write/Member/Contributor, dependendo do contexto).

---

# O que o Build permite?

Imagine o modelo como um banco de LEGO.

Read:

```
Você pode olhar o castelo.
```

Build:

```
Você pode usar as mesmas peças
para montar outro castelo.
```

Write:

```
Você pode trocar as peças do estoque.
```

Essa analogia costuma ajudar bastante.

---

# Relação com Analyze in Excel

Quando o Excel conecta ao modelo:

```
Excel

↓

Power BI

↓

Modelo Semântico
```

O Excel faz consultas MDX/DAX ao modelo.

Isso é considerado uma forma de **construir uma nova análise**.

Por isso:

**Analyze in Excel exige Build Permission.**

---

# Relação com "Criar Relatório"

No Power BI Service existe a opção:

```
Novo Relatório

↓

Usar Modelo Semântico Existente
```

Quem precisa dessa permissão?

Resposta:

✅ Build.

---

# Pegadinha da PL-300

Questão:

> "Os usuários devem conseguir analisar os dados no Excel, mas não podem alterar o modelo."

Resposta:

✅ Build Permission.

---

Questão:

> "Os usuários apenas visualizarão dashboards."

Resposta:

✅ Read.

---

Questão:

> "Os usuários irão modificar tabelas e medidas."

Resposta:

❌ Build não basta.

---

# Comparação

| Permissão  | Visualizar | Criar relatório usando o modelo | Analyze in Excel | Editar modelo |
| ---------- | ---------- | ------------------------------- | ---------------- | ------------- |
| Read       | ✅          | ❌                               | ❌                | ❌             |
| Build      | ✅          | ✅                               | ✅                | ❌             |
| Write/Edit | ✅          | ✅                               | ✅                | ✅             |