Telecom X – Parte 2: Previsão de Churn de Clientes
🧠 Descrição do Projeto
Neste projeto, atuamos como Analista de Machine Learning Júnior na Telecom X, com o objetivo de construir modelos preditivos para identificar clientes com maior risco de cancelar os serviços (churn). Isso permitirá à empresa implementar estratégias de retenção mais eficazes.

🎯 Objetivos
Realizar pré-processamento dos dados (limpeza, encoding, normalização).

Analisar correlações entre variáveis.

Balancear classes usando SMOTE para tratar o desbalanceamento.

Treinar e comparar três modelos de classificação.

Avaliar desempenho dos modelos e gerar insights estratégicos.

🛠️ Etapas do Projeto
🔧 1. Preparação dos Dados
Remoção de colunas irrelevantes e multicolineares (ID único e contas_diarias).

Aplicação de OneHotEncoder para variáveis categóricas via ColumnTransformer.

Normalização com StandardScaler para dados sensíveis à escala.

Balanceamento das classes com SMOTE, equilibrando a proporção de churn (~26%).

📊 2. Análise de Correlação
Correlação negativa moderada entre tenure e churn (-0.35), indicando menor churn com maior tempo de contrato.

Correlações positivas moderadas com monthly_charges (0.19), paperless_billing (0.19) e senior_citizen (0.15).

Remoção de contas_diarias por multicolinearidade perfeita com monthly_charges.

📈 3. Análises Visuais
Boxplots mostraram que clientes que cancelaram possuem menor tempo de contrato e menor gasto total.

Scatterplot reforçou que clientes de longo prazo e alto gasto total têm menor propensão a churn.

✂️ 4. Separação dos Dados
Divisão estratificada em treino (70%) e teste (30%) mantendo a proporção de churn.

🤖 5. Modelos Treinados
Regressão Logística (linear, requer normalização).

Random Forest (baseado em árvore, não requer normalização).

KNN (baseado em distância, requer normalização).

📊 6. Avaliação dos Modelos
Métrica	Regressão Logística	Random Forest (Otimizado)	KNN
Acurácia	75%	78%	69%
Precisão (Churn)	52%	59%	45%
Recall (Churn)	80%	55%	72%
F1-score (Churn)	0.63	0.57	0.55
AUC	0.8443	0.8385	0.7545

Regressão Logística apresentou melhor desempenho geral, com maior AUC e recall, ideal para identificar clientes em risco.

Random Forest teve maior precisão, mas menor recall para churn.

KNN apresentou desempenho inferior aos demais.

 📌 7. Principais Fatores de Churn Identificados
Tempo de contrato (clientes com menor tenure mais propensos a churn).

Tipo de contrato (contratos mensais associam-se a maior churn).

Serviço de internet (fibra óptica está ligado a maior evasão).

Método de pagamento (cheque eletrônico aumenta risco).

Valores de cobranças mensais e totais influenciam na rotatividade.

 🚀8. Estratégias de Retenção Recomendadas
Focar em clientes nos primeiros meses e com contratos mensais, oferecendo suporte e incentivos.

Investigar satisfação e custo do serviço de fibra óptica.

Analisar clientes que pagam com cheque eletrônico para identificar possíveis melhorias.

Incentivar migração para contratos de maior duração com benefícios.

Comunicar-se de forma personalizada com clientes em risco usando os insights do modelo.

Como Executar
Clone o repositório:

bash
Copiar
Editar
git clone https://github.com/MateusSanfer/Telecom-X-Parte-2-Prevendo-Churn.git
cd Telecom-X-Parte-2-Prevendo-Churn
Instale as dependências:

bash
Copiar
Editar
pip install -r requirements.txt
Carregue os dados tratados via código Python:

python
Copiar
Editar
import pandas as pd

url_dados_tratados = 'https://raw.githubusercontent.com/MateusSanfer/Challenge-Telecom-X-One/refs/heads/main/dados_tratados.csv'

dados_tratados = pd.read_csv(url_dados_tratados)
print(dados_tratados.head())
