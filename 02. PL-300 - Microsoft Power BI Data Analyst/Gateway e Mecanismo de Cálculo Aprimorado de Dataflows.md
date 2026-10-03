
Na prática, o **On-premises Data Gateway** é **sempre instalado em uma máquina Windows que tenha acesso às fontes de dados**. Essa máquina pode estar:

- ✅ em um servidor na empresa (o mais comum);
- ✅ em uma máquina virtual no Azure;
- ✅ em outra nuvem (AWS, GCP etc.);
- ✅ até em um computador ligado continuamente (não recomendado para produção).

O importante **não é onde a máquina está fisicamente**, mas sim que ela consiga acessar a fonte de dados.

Permite ao Power BI acessar:

- SQL Server
- Oracle
- Excel
- arquivos locais

Sem ele, o Service não consegue acessar dados locais automaticamente.

---

# Existem dois tipos de gateway

## 1. On-premises Data Gateway (Standard)

É o que normalmente chamamos apenas de "Gateway".

Ele é usado por:

- Power BI
- Power Apps
- Power Automate
- Azure Analysis Services
- Fabric (em alguns cenários)

Permite que o Power BI Service acesse fontes privadas.

Exemplo:

```
Power BI Service
       │
Internet
       │
Gateway
       │
SQL Server
```

---

## 2. On-premises Data Gateway (Personal Mode)

É praticamente igual, mas:

- só serve para um usuário;
- apenas Power BI;
- não pode ser compartilhado.

Quase nunca aparece na PL-300.

---

## Enhanced Dataflows Compute Engine

É um recurso do Power BI Premium/Fabric que acelera Dataflows.

Ele:

- melhora joins
- melhora merges
- melhora cálculos
- melhora consultas entre Dataflows

Não é obrigatório.

Serve para desempenho.