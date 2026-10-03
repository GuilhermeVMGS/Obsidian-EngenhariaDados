Essas funções fazem parte das **funções DAX de hierarquia pai-filho (Parent-Child Hierarchy)**.

Elas são usadas quando você tem uma estrutura onde um registro aponta para outro registro da mesma tabela.

Exemplo clássico:

- Funcionário → Gerente
- Conta contábil → Conta pai
- Categoria → Categoria superior

---

## Exemplo de tabela

Tabela Funcionários:

|EmployeeID|Nome|ManagerID|
|---|---|---|
|1|Carlos|BLANK()|
|2|Ana|1|
|3|João|2|
|4|Pedro|3|

Hierarquia:

```
Carlos
 └── Ana
      └── João
           └── Pedro
```

---

# PATH()

Cria uma "caminho" mostrando todos os pais daquele registro.

Sintaxe:

```
PATH(<ID>, <ID_PAI>)
```

Exemplo:

```
Caminho =
PATH(Funcionarios[EmployeeID], Funcionarios[ManagerID])
```

Resultado:

|Nome|Caminho|
|---|---|
|Carlos|1|
|Ana|1\|2|
|João|1\|2\|3|
|Pedro|1\|2\|3\|4|

Ele cria uma sequência dos IDs desde o topo até o registro atual.

---

# PATHLENGTH()

Retorna quantos níveis existem no caminho.

Sintaxe:

```
PATHLENGTH(<path>)
```

Exemplo:

```
Niveis =
PATHLENGTH(Funcionarios[Caminho])
```

Resultado:

|Nome|Níveis|
|---|---|
|Carlos|1|
|Ana|2|
|João|3|
|Pedro|4|

Uso:

Descobrir o nível hierárquico.

---

# PATHITEM()

Retorna um item específico dentro do caminho.

Sintaxe:

```
PATHITEM(<path>, <posição>)
```

Exemplo:

```
Gerente Raiz =
PATHITEM(Funcionarios[Caminho],1)
```

Resultado:

|Nome|Gerente raiz|
|---|---|
|Pedro|1|

Porque o primeiro item sempre é o topo.

---

Outro exemplo:

```
Nivel 3 =
PATHITEM(Funcionarios[Caminho],3)
```

Pedro:

```
1 | 2 | 3 | 4

posição 3 = 3
```

Resultado:

João.

---

# PATHCONTAINS()

Verifica se um valor existe dentro do caminho.

Sintaxe:

```
PATHCONTAINS(<path>, <item>)
```

Exemplo:

```
É subordinado do Carlos =
PATHCONTAINS(Funcionarios[Caminho],1)
```

Resultado:

|Funcionário|Resultado|
|---|---|
|Ana|TRUE|
|João|TRUE|
|Pedro|TRUE|

Todos possuem Carlos no caminho.

---

## Resumo PATH

| Função       | Objetivo                      |
| ------------ | ----------------------------- |
| PATH         | Cria a hierarquia             |
| PATHLENGTH   | Conta níveis                  |
| PATHITEM     | Pega um nível específico      |
| PATHCONTAINS | Verifica se existe no caminho |