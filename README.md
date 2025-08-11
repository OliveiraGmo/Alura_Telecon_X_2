# 🌟 Análise de Evasão de Clientes (Churn) na TelecomX 📊

## 🎯 Descrição do Projeto
Este projeto realiza uma análise exploratória e modelagem preditiva para identificar os principais fatores que levam à evasão de clientes (churn) na TelecomX. O objetivo é construir modelos capazes de prever quais clientes têm maior probabilidade de evadir e fornecer insights para estratégias de retenção.

## 💾 Fonte de Dados
Os dados utilizados nesta análise foram obtidos a partir de um arquivo CSV disponível em um repositório GitHub. 📦

## 🚀 Etapas da Análise
Nossa análise seguiu um fluxo metodológico claro, dividido nas seguintes etapas principais:

**1. Carregamento e Exploração Inicial 📥**
- Carregamento dos dados a partir da URL fornecida em um DataFrame pandas.
- Análise das informações básicas do DataFrame, tipos de dados e verificação de valores nulos (`df.info()`).
- Verificação de valores únicos em colunas categóricas.

**2. Limpeza Inicial dos Dados ✨**
- Remoção da coluna 'ID_Cliente', que não seria utilizada na modelagem.

**3. Encoding das Variáveis Categóricas 🔄**
- Aplicação de One-Hot Encoding nas variáveis categóricas ('Sexo_Cliente', 'Servico_Internet', 'Contrato_Conta', 'Metodo_Pagamento') utilizando `pd.get_dummies`.
- Conversão do DataFrame resultante para o tipo inteiro.

**4. Verificação da Proporção de Evasão ✅**
- Contagem e cálculo da proporção de clientes ativos e evadidos para verificar o balanceamento das classes.

**5. Análise de Correlação 🧠**
- Cálculo e visualização da matriz de correlação entre as variáveis numéricas, incluindo a variável alvo 'Rotatividade'.
- Análise das variáveis mais correlacionadas com a evasão através de um gráfico de barras.

**6. Visualização de Relações Específicas 📈**
- Geração de box plots para analisar a relação entre 'Tempo_Servico' e 'Encargos_Totais' com a 'Rotatividade'.
- Criação de um scatter plot cruzando 'Tempo_Servico' e 'Encargos_Totais', colorido pela 'Rotatividade', para visualizar padrões de evasão.

**7. Separação de Dados ✂️**
- Divisão do dataset em conjuntos de treino e teste (70/30) utilizando `train_test_split`, com estratificação pela variável alvo.

**8. Criação e Avaliação de Modelos (Inicial) 🤖**
- Implementação e avaliação inicial de dois modelos: Regressão Logística (com `StandardScaler` via `Pipeline`) e Random Forest.
- Utilização do `classification_report` para avaliar métricas como precisão, recall e f1-score em cada modelo.

**9. Balanceamento de Classes com SMOTE⚖️**
- Aplicação da técnica SMOTE (Synthetic Minority Over-sampling Technique) no conjunto de treino para lidar com o desbalanceamento de classes da variável 'Rotatividade'.

**10. Criação e Avaliação de Modelos (com SMOTE) 🤖**
- Treinamento e avaliação dos modelos Regressão Logística (com `StandardScaler` via `Pipeline`) e Random Forest utilizando os dados de treino balanceados com SMOTE.
- Avaliação dos modelos no conjunto de teste original utilizando a função `avaliar_modelo`, que exibe métricas e a matriz de confusão.

**11. Ajuste de Hiperparâmetros (Grid Search) ⚙️**
- Utilização de `GridSearchCV` para encontrar os melhores hiperparâmetros para a Regressão Logística e Random Forest, buscando otimizar o f1-score.
- Treinamento dos modelos ajustados com os melhores parâmetros nos dados de treino balanceados com SMOTE.

**12. Avaliação dos Modelos Ajustados ✅**
- Avaliação final dos modelos de Regressão Logística e Random Forest com os hiperparâmetros ajustados no conjunto de teste original, apresentando métricas e matrizes de confusão.

**13. Análise de Importância das Variáveis 📊**
- Extração e análise dos coeficientes da Regressão Logística para entender a influência de cada variável na probabilidade de evasão.
- Extração e visualização da importância das features do modelo Random Forest para identificar as variáveis mais relevantes na previsão de churn.

**14. Conclusão e Estratégias de Retenção 📝**
- Resumo dos resultados da análise de correlação e importância das variáveis.
- Proposição de estratégias de retenção baseadas nos insights extraídos dos modelos e da análise exploratória.

* * *
