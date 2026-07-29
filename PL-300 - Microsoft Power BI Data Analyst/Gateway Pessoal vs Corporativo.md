
No Power BI, a diferença principal entre o **Gateway Pessoal (Personal Mode)** e o **Gateway Padrão/Corporativo (Standard / Enterprise Mode)** é **quem pode usar o gateway e para qual cenário ele foi criado**.

Pense no Gateway como uma **ponte entre o Power BI Service (nuvem) e dados que estão dentro da sua rede local** (servidor SQL Server, arquivos locais, Oracle, etc.).

```
Power BI Service (nuvem)
          |
          |
     Gateway
          |
          |
Banco local / arquivos / servidores internos
```

## 1. Gateway Pessoal (Personal Mode)

É o gateway feito para **um único usuário**.

### Características:

✅ Instalação simples  
✅ Uso individual  
✅ Normalmente usado para relatórios pessoais  
❌ Não permite compartilhamento do gateway com outros usuários  
❌ Não suporta cenários corporativos complexos

Exemplo:

> João criou um relatório no Power BI Desktop conectado em um Excel no computador dele.

Ele instala o **Gateway Pessoal**.

Quando publica:

```
Power BI Service
        |
        |
Gateway Pessoal do João
        |
        |
C:\Dados\Vendas.xlsx
```

O Power BI consegue atualizar os dados automaticamente.

Mas:

Maria não consegue usar esse gateway para atualizar o relatório dela.

---

### Limitações do Personal Mode:

- Apenas o usuário que instalou gerencia o gateway.
- Não permite múltiplas conexões compartilhadas.
- Não suporta cenários com vários desenvolvedores.
- Não é indicado para empresa.

---

# 2. Gateway Padrão / Corporativo (Standard / Enterprise Mode)

É o gateway usado em empresas.

Ele permite que **vários usuários e vários relatórios usem a mesma infraestrutura**.

Exemplo:

Uma empresa possui:

- SQL Server local
- Oracle
- Arquivos em rede
- Relatórios Power BI usados por 200 funcionários

Instala um Gateway Standard em um servidor:

```
                 Power BI Service
                       |
                       |
              Gateway Corporativo
                       |
       --------------------------------
       |              |               |
   SQL Server      Oracle       Arquivos
```

Vários usuários podem publicar relatórios usando esse gateway.

---

## Comparação direta

| Característica                 | Personal Mode | Standard / Enterprise |
| ------------------------------ | ------------- | --------------------- |
| Uso                            | Individual    | Empresa               |
| Compartilhamento               | ❌ Não         | ✅ Sim                 |
| Vários usuários                | ❌             | ✅                     |
| Administração central          | ❌             | ✅                     |
| Power BI Service               | ✅             | ✅                     |
| Atualização agendada           | ✅             | ✅                     |
| DirectQuery                    | ❌ Limitado    | ✅                     |
| Live Connection                | ❌             | ✅                     |
| Cluster / alta disponibilidade | ❌             | ✅                     |
| Segurança corporativa          | Básica        | Avançada              |