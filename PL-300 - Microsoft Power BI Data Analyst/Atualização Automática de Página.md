
## O que é?

A **Atualização Automática de Página (Auto Page Refresh - APR)** faz com que um relatório seja atualizado automaticamente em intervalos definidos, sem que o usuário precise apertar F5 ou clicar em Atualizar.

Exemplo:

Um painel acompanha o preço de ações.

```
09:00:00
PETR4 = R$ 35,20

↓

09:00:05
PETR4 = R$ 35,18

↓

09:00:10
PETR4 = R$ 35,25
```

O relatório atualiza sozinho.

---

## Quando ela funciona?

A APR foi criada principalmente para cenários **quase em tempo real**, então ela funciona com:

- ✅ DirectQuery
- ✅ Algumas configurações com Live Connection

Ela **não foi pensada para modelos Import**, pois os dados já estão carregados na memória.

---

## Por que usar DirectQuery?

Imagine:

```
Banco SQL
      ↑
Power BI
```

Cada atualização faz uma nova consulta ao banco.

Se atualizar a cada 5 segundos:

```
12 consultas por minuto

720 consultas por hora

17.280 consultas por dia
```

Agora imagine 500 usuários...

Por isso a Microsoft colocou mecanismos de proteção.

---

# O Intervalo Mínimo de Atualização (Minimum Refresh Interval)

Em uma capacidade Premium/Fabric existe um administrador.

Ele pode definir:

```
Menor intervalo permitido:

30 minutos
```

Ou

```
5 minutos
```

Ou

```
5 segundos
```

---

Imagine:

O desenvolvedor tenta configurar:

```
Atualizar a cada

5 segundos
```

Mas a capacidade diz:

```
Mínimo permitido

30 minutos
```

O Power BI simplesmente trava a opção.

Você não consegue escolher um valor menor.