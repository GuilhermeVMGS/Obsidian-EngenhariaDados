Visual utilizado para analisar a distribuição de frequência em um conjunto de dados contínuos.

Imagine que você é dono de uma loja de roupas e quer saber a **idade dos seus clientes** para decidir o que comprar para o estoque. Você anota a idade de 20 clientes:

> 15, 17, 18, 22, 23, 24, 25, 28, 31, 33, 35, 37, 41, 42, 44, 46, 52, 53, 58, 62

Fica difícil ver um padrão olhando só para essa lista de números soltos, certo?

O **histograma** resolve isso. Ele junta os números em "grupos" (faixas de idade) e conta quantas pessoas estão em cada um:

1. **Organizando os dados em faixas**

- **De 10 a 20 anos:** 3 clientes (15, 17, 18)
- **De 21 a 30 anos:** 5 clientes (22, 23, 24, 25, 28)
- **De 31 a 40 anos:** 4 clientes (31, 33, 35, 37)
- **De 41 a 50 anos:** 4 clientes (41, 42, 44, 46)
- **De 51 a 60 anos:** 3 clientes (52, 53, 58)
- **De 61 a 70 anos:** 1 cliente (62)

2. **Transformando em Gráfico**

Agora, o histograma transforma esses grupos em barras coladas:

- A barra de "21 a 30 anos" será a **mais alta**, porque tem 5 pessoas.
- A barra de "61 a 70 anos" será a **mais baixa**, com apenas 1 pessoa.

**Resumo prático**

O histograma é uma ferramenta visual que serve para você olhar para um monte de números e descobrir, num piscar de olhos, **onde está a maioria das coisas** e **onde está a minoria**.
### Como construir no Power BI:

1. Clique com o botão direito sobre a coluna numérica no painel de dados e selecione **Novo Grupo**.   
2. Defina o tipo de grupo como **Caixas (Bins)**.
3. Configure o intervalo desejado:
- **Tamanho da caixa:** Determina a largura de cada intervalo (ex.: faixas de 10 em 10).
- **Número de caixas:** O usuário define a quantidade de barras e o Power BI calcula a largura de cada intervalo.
1. Utilize essa nova coluna de Bins no eixo X de um gráfico de colunas para visualizar a distribuição.

![[Pasted image 20260729171326.png]]
