A **Detecção de Anomalias (Anomaly Detection)** no Power BI é um recurso nativo de Inteligência Artificial que identifica automaticamente picos ou quedas fora do padrão histórico em dados de séries temporais.

## 1. Como a Detecção de Anomalias Funciona?

O Power BI analisa a série histórica do visual usando modelos de Machine Learning para calcular um **intervalo de confiança** (a faixa esperada onde os valores deveriam estar).

- Se um ponto de dado fica **acima do limite superior** ou **abaixo do limite inferior**, ele é sinalizado com um indicador visual (um ponto destacado no gráfico).
- Ao clicar no ponto anômalo, o Power BI abre o painel **Explicação da Anomalia** e analisa outras dimensões do modelo para apontar a causa provável (ex: _"A queda de vendas neste dia coincidiu com uma queda acentuada na Categoria Eletrônicos"_).    

## 2. Requisitos de Uso

Para ativar a Detecção de Anomalias no Power BI Desktop:

1. O visual deve ser obrigatoriamente um **Gráfico de Linhas (Line Chart)**.
2. O eixo do gráfico deve conter um campo no formato de **Data/Hora** (série temporal).
3. O campo de data no eixo precisa conter dados em um nível de granularidade contínuo (Ex: _Dia, Mês, Ano_).

![[Pasted image 20260730155827.png]]
