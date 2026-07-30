
# 1. O que é o Microsoft Access?

O **Microsoft Access** é um sistema de banco de dados relacional da Microsoft, muito usado em:

- sistemas legados
- pequenas aplicações internas
- controles departamentais

Ele armazena dados normalmente em arquivos:

```
.accdb
```

ou antigos:

```
.mdb
```

Exemplo:

```
\\Servidor\Financeiro\Estoque.accdb
```

---

# 2. Como o Power BI conecta no Access?

No Power BI Desktop:

```
Obter Dados
    ↓
Banco de Dados Access
    ↓
Selecionar arquivo .accdb
```

O Power BI usa o **driver do Access Database Engine** para ler o arquivo.

---

# 3. O ponto mais importante da PL-300: Access local ≠ Power BI Service

No Desktop:

```
Power BI Desktop
        |
        ↓
Arquivo Access
```

Funciona porque sua máquina consegue acessar o arquivo.

---

Mas no Service:

```
Power BI Service (nuvem)
        |
        X
Arquivo Access na rede interna
```

Não funciona diretamente.

Por quê?

Porque o Service está na Microsoft Cloud e não enxerga sua rede privada.

---

# 4. Solução: On-premises Data Gateway

Quando a fonte está local:

```
Access
  |
  |
Gateway
  |
  |
Power BI Service
```

O gateway:

- fica instalado na rede da empresa
- acessa o Access
- envia dados para o Power BI Service

---

# 5. Quando usar Gateway com Access?

Use quando:

✅ Arquivo Access está:

- no computador local
- em servidor interno
- em compartilhamento de rede

Exemplo:

```
\\Servidor01\Dados\Estoque.accdb
```

E você quer:

- atualização agendada
- dashboard publicado no Service

---

# 6. Atualização agendada

Cenário típico da prova:

Sistema legado:

```
08:00 → atualiza Access
09:00 → atualiza Access
10:00 → atualiza Access
```

Power BI:

```
08:30 → Refresh
09:30 → Refresh
10:30 → Refresh
```

O gateway busca os dados novos.

---

# 7. Access em OneDrive/SharePoint é diferente

Pegadinha comum.

## Access local:

```
C:\Dados\Base.accdb
```

ou

```
\\Servidor\Base.accdb
```

➡️ Gateway

---

## Arquivo em SharePoint Online:

```
SharePoint
    |
    ↓
Power BI Service
```

Normalmente:

➡️ Não precisa Gateway

Porque já está na nuvem.

---

# 8. Access e DirectQuery

Outro ponto importante:

Access normalmente é usado com:

✅ Import Mode

Não é uma fonte típica para:

❌ DirectQuery

Por quê?

O Power BI geralmente importa os dados para o modelo.

Fluxo:

```
Access
   ↓
Power BI
   ↓
Modelo VertiPaq
```

---

# 9. Access e atualização quase em tempo real

Cuidado.

A questão fala:

> "quase atualizados ao longo do dia"

Não significa:

"tempo real".

Access normalmente trabalha com:

- atualização agendada

Exemplo:

```
Atualizar a cada hora
```

Não:

```
Atualização instantânea
```

---

# 10. Limitações do Access que podem aparecer

## Volume

Access não é indicado para:

- milhões/bilhões de registros
- grandes data warehouses

Exemplo:

Melhor:

```
Azure Synapse
SQL Server
Dataverse
```

---

## Concorrência

Muitos usuários gravando ao mesmo tempo podem gerar problemas.

---

## Arquivo único

O banco é um arquivo.

Exemplo:

```
Estoque.accdb
```

Diferente de:

```
SQL Server
  |
  ├── tabelas
  ├── índices
  └── serviços
```

---

# 11. Comparação para PL-300

| Fonte                        | Precisa Gateway?  |
| ---------------------------- | ----------------- |
| Access local                 | ✅ Sim             |
| SQL Server local             | ✅ Sim             |
| Oracle local                 | ✅ Sim             |
| Excel local                  | ✅ Sim             |
| SharePoint Online            | ❌ Normalmente não |
| OneDrive pessoal/empresarial | ❌ Normalmente não |
| Azure SQL                    | ❌ Normalmente não |
| Azure Synapse                | ❌ Normalmente não |