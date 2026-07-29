
### Parse

Significa:

> Interpretar ou converter um valor de um formato para outro.

Exemplos:

Converter texto para data:

```
Date.FromText("2026-07-29")
```

Texto:

```
"100"
```

para número:

```
Number.FromText("100")
```

### Web.Contents()

## O que é?

`Web.Contents()` é uma função do Power Query (linguagem M) usada para acessar conteúdo da Web.

Muito usada para:

- APIs;
- arquivos online;
- serviços REST.

Sintaxe:

```
Web.Contents(url)
```

---

Exemplo:

```
Web.Contents(
"https://api.exemplo.com/vendas"
)
```

O Power BI acessa essa URL.

---

## Exemplo com API:

```
Json.Document(
    Web.Contents(
        "https://api.empresa.com/clientes"
    )
)
```

Fluxo:

```
API
 ↓
Web.Contents()
 ↓
JSON
 ↓
Power Query
 ↓
Modelo
	```