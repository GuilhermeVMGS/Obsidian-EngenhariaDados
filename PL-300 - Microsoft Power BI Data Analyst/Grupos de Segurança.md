
Na atribuição de papéis de **Segurança em Nível de Linha (RLS)** no Power BI Service, a Microsoft restringe a adição apenas aos seguintes tipos de grupos e identidades de e-mail:

1. **Grupos de Segurança do Entra ID (Azure AD Security Group)**
2. **Grupos Habilitados para Correio Eletrônico (Mail-Enabled Security Group)**
3. **Grupos de Distribuição (Distribution Group)**
4. **Usuários individuais** (internos e convidados B2B)

No Power BI, **grupos de segurança** são grupos de usuários criados geralmente no **Microsoft Entra ID (antigo Azure AD)** para facilitar o gerenciamento de permissões.

Eles são muito usados com **RLS (Row-Level Security / Segurança em Nível de Linha)** porque você não precisa colocar usuário por usuário dentro da regra.

---

## 1. O que é um grupo de segurança?

Imagine uma empresa com:

- 5 vendedores de Minas Gerais
- 10 vendedores de São Paulo
- 20 vendedores do Rio

Em vez de criar regras assim:

```
João → vê MG
Maria → vê MG
Pedro → vê SP
Ana → vê SP
...
```

Você cria grupos:

```
Grupo_Vendedores_MG
        |
        ├── João
        ├── Maria
        └── Carlos


Grupo_Vendedores_SP
        |
        ├── Pedro
        ├── Ana
        └── Lucas
```

O Power BI verifica:

> "Esse usuário pertence a qual grupo?"

E aplica a segurança.

---

# 2. Como funciona com RLS?

Suponha uma tabela de vendas:

### Fato_Vendas

|Venda|Estado|Valor|
|---|---|---|
|1|MG|1000|
|2|MG|500|
|3|SP|800|
|4|RJ|900|

Você cria uma tabela de segurança:

### Permissao

|Grupo|Estado|
|---|---|
|Grupo_Vendedores_MG|MG|
|Grupo_Vendedores_SP|SP|
|Grupo_Vendedores_RJ|RJ|

Relacionamento:

```
Permissao
    |
    |
Fato_Vendas
```

---

Na regra RLS você usa algo como:

```
[Grupo] = USERPRINCIPALNAME()
```

ou uma lógica baseada no usuário/grupo.

Quando João abre o relatório:

```
João
 |
pertence ao grupo
 |
Grupo_Vendedores_MG
 |
permite MG
 |
Fato_Vendas filtrada
```

Ele vê:

|Estado|Valor|
|---|---|
|MG|1000|
|MG|500|

Ele não vê SP ou RJ.

---

# 3. Por que usar grupo em vez de usuário?

Imagine uma empresa com 500 vendedores.

Sem grupo:

```
RLS:
João → MG
Maria → MG
Carlos → MG
Pedro → SP
...
```

Manutenção horrível.

Com grupos:

```
RLS:
Grupo_Vendedores_MG → MG
Grupo_Vendedores_SP → SP
```

Entrou funcionário novo?

Só adiciona ele no grupo.

O Power BI automaticamente aplica a regra.

---

# 4. Onde esses grupos são criados?

Normalmente no:

Microsoft Entra ID

ou no ambiente corporativo do Microsoft 365.

Exemplo:

```
Entra ID

Grupo:
BI_Financeiro

Membros:
- João
- Maria
- Carlos
```

Depois esse grupo é adicionado na segurança do dataset no Power BI Service.

---

# 5. Configurando no Power BI Service

No workspace:

```
Dataset
   ↓
Segurança
   ↓
Adicionar grupo
```

Você coloca:

```
Grupo_Vendedores_MG
```

em uma função RLS:

```
Função: Vendas_MG
Filtro:
Estado = "MG"
```

Agora qualquer pessoa dentro do grupo recebe essa permissão.