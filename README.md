## Predição de Doenças Cardíacas com XGBoost ❤️

![Static Badge](https://img.shields.io/badge/Status-Finalizado-green)

## Descrição

Este projeto, desenvolvido durante o curso da Alura, utiliza o algoritmo XGBoost para prever a presença de doenças cardíacas em pacientes com base em um conjunto de dados clínicos. O modelo foi treinado e avaliado utilizando técnicas de validação cruzada e otimização de hiperparâmetros.

## Tecnologias Utilizadas

- Python
- Pandas
- Scikit-learn
- XGBoost
- Plotly

## Dicionário de Dados

| Coluna | Descrição | Tipo de Dado |
|---|---|---|
| Idade | Idade em anos | Numérico |
| Sexo | Sexo biológico (0 = feminino, 1 = masculino) | Categórico |
| Tipo dor | Tipo de dor no peito (1 = angina típica, 2 = angina atípica, 3 = não angina, 4 = angina assintomática) | Categórico |
| Pressao arterial | Pressão arterial em repouso (mmHg) | Numérico |
| Colesterol | Nível de colesterol no sangue (mg/dl) | Numérico |
| Glicemia jejum >120 | Nível de glicose no sangue em jejum (0 = abaixo de 120 mg/dl, 1 = acima de 120 mg/dl) | Categórico |
| Resultados ECG | Resultados do eletrocardiograma em repouso (0 = normal, 1 = anormalidade de onda ST-T, 2 = hipertrofia ventricular esquerda) | Categórico |
| Frequencia cardiaca max | Frequência cardíaca máxima durante teste de esforço | Numérico |
| Dor exercicio | Angina induzida por exercício (0 = sim, 1 = não) | Categórico |
| Depressao ST | Depressão do segmento ST induzida por exercício em relação ao repouso | Numérico |
| Inclinacao ST | Inclinação do segmento ST no pico do exercício (1 = inclinado para cima, 2 = plano, 3 = inclinado para baixo) | Categórico |
| Numero vasos fluro | Número de vasos sanguíneos principais coloridos por fluoroscopia | Numérico |
| Teste cintilografia | Resultado do teste de estresse com tálio (3 = normal, 6 = defeito fixo, 7 = defeito reversível) | Categórico |
| Doenca cardiaca | Presença de doença cardíaca (0 = Ausência, 1 = Presença) | Categórico |

## Descrição Detalhada do Projeto

### Análise Exploratória de Dados:

- Foi realizada uma análise exploratória dos dados para entender a distribuição das variáveis e sua relação com a presença de doença cardíaca.
- Histogramas e boxplots foram utilizados para visualizar a distribuição das variáveis e identificar possíveis padrões.

### Pré-processamento de Dados:

- A variável alvo "Doenca cardiaca" foi convertida para valores numéricos (0 e 1).
- Os dados foram divididos em conjuntos de treino e teste utilizando estratificação para garantir a proporção de classes em ambos os conjuntos.

### Modelagem:

1. **Modelo Baseline:** Um modelo Decision Tree Classifier foi treinado como baseline para comparação com o XGBoost.

2. **XGBoost:** O algoritmo XGBoost foi utilizado para construir o modelo preditivo.

### Otimização de Hiperparâmetros:

- **RandomizedSearchCV:** Foi utilizada a técnica RandomizedSearchCV para encontrar os melhores hiperparâmetros para o modelo XGBoost, explorando um espaço de busca predefinido.
- **GridSearchCV:**  A técnica GridSearchCV também foi utilizada para uma busca mais exaustiva dentro de um espaço de hiperparâmetros mais restrito.

### Avaliação do Modelo:

- **Métricas de Classificação:** Acurácia, precisão, recall e F1-score foram calculadas para avaliar o desempenho do modelo.
- **Matriz de Confusão:** Uma matriz de confusão foi gerada para visualizar a performance do modelo em cada classe.
- **Curva ROC:** A curva ROC foi plotada para analisar a capacidade de discriminação do modelo.

### Pipeline:

- Um pipeline do Scikit-learn foi criado para encapsular o modelo XGBoost, permitindo a aplicação de transformações e treinamento do modelo em uma única etapa.

### Salvamento do Modelo:

- O modelo treinado foi salvo em um arquivo .pkl utilizando a biblioteca joblib, permitindo sua reutilização posterior.

### Utilização do Modelo:

- O modelo salvo foi carregado e utilizado para fazer previsões em um novo conjunto de dados de pacientes.
- As previsões foram adicionadas ao DataFrame original para visualização.
