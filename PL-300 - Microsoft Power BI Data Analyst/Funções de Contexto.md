
### `EARLIER` (Acessar contexto anterior)

- **O que faz:** Durante uma iteração linha por linha (Contexto de Linha), a `EARLIER` pega o valor da linha no **loop mais externo**.

- **Exemplo de uso antigo:** Calcular o acumulado linha por linha em uma Coluna Calculada:
![[Pasted image 20260729165355.png]]
**Atenção para a PL-300:** A própria Microsoft recomenda **NÃO usar mais a `EARLIER`**. Hoje em dia se usam **Variáveis (`VAR`)**, que armazenam o valor da linha antes de entrar na filtragem: