Opção:

```
Enable report readers to personalize visuals
```

Permite que o usuário altere, no service:

- tipo do gráfico
- eixo
- legenda
- medidas

Sem modificar o relatório original.

É uma personalização individual.

Mais especificamente:

1. O autor publica o relatório no **Power BI Service**.
2. Abre o relatório em modo de edição.
3. Nas configurações do relatório ou do visual, habilita **Personalize visuals**.
4. Os usuários com permissão para visualizar o relatório podem personalizar os visuais.

### O que o leitor pode fazer?

Se o autor permitir, o leitor pode:

- Alterar o tipo de visual (barra, coluna, pizza, etc.).
- Trocar campos dos eixos.
- Alterar a legenda.
- Adicionar ou remover medidas (dentro do que foi permitido).

### O que ele **não** faz?

- ❌ Não altera o relatório original.
- ❌ Não publica as alterações para outros usuários.
- ❌ Não modifica o modelo de dados.
- ❌ Não cria novas medidas DAX.

As personalizações são **temporárias ou salvas apenas para aquele usuário**, dependendo da funcionalidade disponível.

### Exemplo

O relatório original possui:

- **Gráfico de barras** mostrando **Vendas por Estado**.

Você prefere visualizar **Vendas por Categoria** em um **gráfico de pizza**.

Se **Personalize visuals** estiver habilitado, você pode fazer essa alteração para sua visualização, sem impactar os demais usuários nem o relatório original.

### Para a PL-300

A ideia principal para decorar é:

- **Autor do relatório** → habilita a personalização.
- **Leitor do relatório** → pode personalizar os visuais para si.
- **Relatório original permanece inalterado.**

Essa última frase costuma aparecer bastante nas questões da prova.