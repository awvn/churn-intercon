### Project - Churn (Empresa de Telecom e Tech)

**Problema de Negócio:** Identificar clientes com elevado risco de cancelar serviços de telecomunicações para apoiar campanhas preventivas de retenção

**Solução:** Unificação de múltiplas bases de dados, engenharia de atributos (tenure, faturação) e comparação entre Regressão Logística, Random Forest e Gradient Boosting. Sendo o Gradient Boosting o campeão ao alcançar a melhor performance com AUC-ROC de 0.9084, com 86.23% de acurácia.
Os resultados conseguidos neste projeto, foram obtidos em um ambiente experimental (PoC), que poderão ser diferentes em outras circunstâncias. Por isso os mesmos devem passar por uma validação rigorosa antes de ir para operação real.

## ⚠️ Limitações e Evolução Futura

### Limitações dos Dados e do Modelo
* **Cenário Experimental vs. Produção:** Os resultados alcançados com o modelo **Gradient Boosting** (**AUC-ROC de 0.9084** e **86,23% de acurácia**) foram obtidos sobre uma base histórica estática em ambiente de desenvolvimento. Essas métricas demonstram o poder discriminativo do algoritmo neste conjunto específico, mas **não representam garantia de desempenho contínuo em produção**, onde o comportamento do consumidor muda ao longo do tempo (*concept drift*).
* **Desbalanceamento e Contexto Operacional:** Em problemas reais de *churn* em telecomunicações, a taxa de cancelamento costuma ser desbalanceada e influenciada por fatores externos não presentes no dataset (como promoções da concorrência, falhas pontuais de rede ou atendimento ao cliente recente). Além disso, a acurácia isolada pode mascarar falsos negativos caso o limiar de decisão (*threshold*) não seja ajustado ao custo financeiro de retenção.

### Melhorias Futuras
* **Otimização Orientada ao Negócio:** Calibrar o limiar de classificação (*threshold tuning*) priorizando **Recall** e **F1-Score** de acordo com o custo de cada campanha de retenção versus o valor do cliente (*LTV*).
* **Engenharia de Atributos Temporais:** Incorporar variáveis comportamentais recentes (ex: queda no volume de chamadas/dados nos últimos 30 dias ou aumento de chamados de suporte).
* **Monitoramento e MLOps:** Implementar uma pipeline de validação temporal, explicabilidade das previsões com **SHAP values** para orientar a equipa comercial e monitoramento contínuo de *data drift* antes de qualquer implantação em ambiente real.


### 🚀 Tecnologias
- Python
- Pandas
- Matplotlib
- seaborn
- Sklearn
- XGBoost
- Logistic Regression

### 📦 Como instalar

``` bash
git clone https://github.com/awvn/churn-intercon.git
cd churn-intercon
pip install -r requirements.txt
