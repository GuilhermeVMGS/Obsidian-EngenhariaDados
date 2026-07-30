

## 1. Permissões da Workspace

Elas dizem:

> **"O que você pode fazer dentro da área de trabalho?"**

São os papéis:

- Admin
- Member (Membro)
- Contributor (Colaborador)
- Viewer (Visualizador)

Exemplo:

```
Workspace

├── Relatórios
├── Dashboards
├── Modelos Semânticos
└── Dataflows
```

Esses papéis controlam o acesso à **workspace inteira**.

---

## 2. Permissões do Modelo Semântico (Dataset/Semantic Model)

Elas dizem:

> **"O que você pode fazer com ESTE modelo semântico específico?"**

Exemplos:

- Read
- Build
- Reshare
- (e permissões de edição, quando aplicáveis)

Essas permissões são concedidas no próprio modelo.

---

# Vamos comparar

Imagine a Workspace:

```
Workspace Financeiro

├── Relatório Vendas
├── Dashboard Executivo
└── Modelo Semântico Vendas
```

João é:

```
Viewer
```

O que isso significa?

Ele pode:

✅ Abrir a Workspace

✅ Ver relatórios

Mas...

Isso **não significa automaticamente** que ele tem Build.

---

# Exemplo

João é Viewer.

Ele abre o relatório normalmente.

Agora tenta:

```
Analyze in Excel
```

Pode aparecer:

```
Acesso negado.
```

Porque ele não recebeu:

```
Build Permission
```

---

# Outro exemplo

Maria recebeu:

```
Build
```

no modelo.

Mesmo sem ser Member da Workspace, ela pode:

```
Excel

↓

Modelo Semântico

↓

Tabela Dinâmica
```

---

# Como elas se relacionam?

Alguns papéis da Workspace **já incluem Build automaticamente**.

Em geral:

|Papel na Workspace|Build incluído?|
|---|---|
|Admin|✅|
|Member|✅|
|Contributor|✅|
|Viewer|❌ (normalmente)|

Ou seja:

Se você é **Member**, normalmente já consegue usar Analyze in Excel porque esse papel inclui Build no modelo semântico.

Mas um **Viewer** normalmente só consegue visualizar o conteúdo. Se precisar criar relatórios ou usar Analyze in Excel, será necessário conceder Build no modelo.

---

# Visualizando a diferença

### Workspace

```
Quem entra na sala?
```

- Admin
- Member
- Contributor
- Viewer

---

### Build

```
O que essa pessoa pode fazer com ESTE modelo?
```

- Criar relatório?
- Analyze in Excel?
- Ferramentas externas?

---

# Analogia

Imagine uma biblioteca.

A Workspace é a biblioteca.

Os papéis são:

Admin

↓

Bibliotecário

Member

↓

Funcionário

Contributor

↓

Auxiliar

Viewer

↓

Visitante

Agora existe um livro específico.

A Build Permission diz:

> "Você pode usar este livro para escrever uma pesquisa."

Não muda seu cargo na biblioteca.

Só muda o que pode fazer com aquele livro.

---

# Por que a Microsoft criou Build?

Imagine que existe um modelo corporativo.

```
Modelo Oficial de Vendas
```

O administrador quer:

- que centenas de pessoas possam criar relatórios;

mas

- ninguém altere o modelo.

A solução é:

```
Build

↓

Pode consultar.

Pode criar.

Não pode editar.
```

---

# O que a PL-300 costuma cobrar?

Questão:

> "Os usuários precisam usar Analyze in Excel."

Resposta:

✅ Build.

---

Questão:

> "Os usuários devem criar novos relatórios usando um modelo existente."

Resposta:

✅ Build.

---

Questão:

> "O usuário deve publicar novos datasets."

Resposta:

❌ Não é Build.