
As descrições abaixo são **tecnologias/protocolos de acesso a dados**, ou seja, maneiras padronizadas de um programa conversar com uma fonte de dados.

# O que acontece quando você faz "Obter Dados > SQL Server"?

Você escolhe:

```
Obter Dados

↓

SQL Server
```

Mas internamente o Power BI usa um **conector nativo** para SQL Server.

Esse conector utiliza tecnologias da Microsoft para se comunicar com o SQL Server (atualmente, principalmente o **SqlClient**). Você **não escolhe OLE DB ou ODBC** nessa conexão.

Ou seja:

> **Quando você usa o conector "SQL Server", você NÃO está usando o conector OLE DB do Power BI.**

---

# Então para que servem ODBC e OLE DB?

O Power BI também possui conectores genéricos.

## ODBC

(Open Database Connectivity)

Padrão aberto. Conecta praticamente qualquer banco.

Exemplo

MySQL
PostgreSQL
SQLite
Firebird

Imagine um banco pouco conhecido.

Ele fornece um **driver ODBC**.

Você instala esse driver e faz:

```
Obter Dados

↓

ODBC

↓

Seleciona o driver
```

Assim o Power BI consegue acessar esse banco.

Exemplos:

- Firebird
- SQLite
- Bancos legados
- Sistemas proprietários

---

## OLE DB

Funciona de forma semelhante.

Você faz:

```
Obter Dados

↓

OLE DB
```

Depois escolhe um **Provider OLE DB**.

É bastante usado em sistemas Microsoft mais antigos.

Criado pela Microsoft. Muito usado com SQL Server e Access.

Normalmente possui melhor integração com tecnologias Microsoft.


---
# ODBC x OLE DB

|ODBC|OLE DB|
|---|---|
|Usa **drivers**|Usa **providers**|
|Padrão aberto|Tecnologia da Microsoft|
|Muito utilizado até hoje|Mais associado a sistemas legados|
|Compatível com diversos bancos|Muito usado com tecnologias Microsoft|

---

## OData

(Open Data Protocol)

Não conecta diretamente em banco.

Conecta em APIs.

Exemplo

```
https://empresa.com/odata/
```

Muito usado em:

- SharePoint
- Dynamics 365
- SAP
- serviços REST compatíveis

---

Resumo

| Tipo   | Uso                                |
| ------ | ---------------------------------- |
| ODBC   | Banco de dados via driver genérico |
| OLE DB | Banco Microsoft e provedores OLE   |
| OData  | Serviços Web e APIs                |