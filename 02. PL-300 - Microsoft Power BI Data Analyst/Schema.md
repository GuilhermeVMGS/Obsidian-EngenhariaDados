
Essa é uma pergunta muito comum.

Um **schema** é uma forma de organizar objetos dentro de um banco.

Pense no banco como uma empresa:

```
Banco de Dados
│
├── Financeiro
│      ├── Clientes
│      └── Pagamentos
│
├── Vendas
│      ├── Produtos
│      └── Pedidos
│
└── RH
       ├── Funcionarios
       └── Salarios
```

Essas pastas seriam os schemas.

---

Tecnicamente:

Um schema agrupa:

- Tabelas
- Views
- Procedures
- Funções

---

## Por que escolher o esquema correto é importante?

Porque melhora:

### 1. Organização

Exemplo:

Ruim:

```
Clientes
Clientes2
Clientes_Final
Clientes_Novo
```

Bom:

```
CRM.Clientes
Financeiro.Clientes
```

---

### 2. Segurança

Você pode dar acesso:

```
Usuário Financeiro

Acesso:
Financeiro.*
```

Mas não:

```
RH.*
```

---

### 3. Manutenção

Facilita encontrar objetos.

---

## Resposta para o analista:

> "Um esquema organiza objetos do banco, facilita segurança, manutenção e governança dos dados."