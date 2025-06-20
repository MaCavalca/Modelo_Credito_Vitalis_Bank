# 💳 Vitalis Bank - Primeiro Modelo de Concessão de Crédito

Este projeto apresenta o **primeiro modelo de concessão de crédito do Vitalis Bank**, construído com foco em **robustez, modularidade e explicabilidade**. Utilizamos algoritmos de ponta como **XGBoost** e **LightGBM**, estruturando todo o processo com base nas etapas do **CRISP-DM**, que incluem:

- Entendimento do negócio 🧠
- Entendimento dos dados 🔍
- Preparação de dados ⚙️
- Modelagem 🧪
- Avaliação 📊

Nosso objetivo é identificar potenciais inadimplentes com precisão, garantindo decisões de crédito mais seguras e sustentáveis.

---

## 🗂️ Dados Utilizados

Os dados foram obtidos da competição Kaggle:

**PoD Academy - Análise de Crédito para Fintech**  
🔗 [Link para a competição](https://www.kaggle.com/competitions/pod-academy-analise-de-credito-para-fintech/data)

Foram utilizadas **3 tabelas principais**:

- `application_train.csv` / `application_test.csv`  
  Contêm os dados de treino e teste com informações de clientes e a variável alvo `TARGET` (1 = inadimplente, 0 = adimplente)

- `previous_application.csv`  
  Histórico de aplicações anteriores de empréstimo por cliente

- `bureau.csv`  
  Informações de crédito do cliente junto a outras instituições

📉 Para garantir maior controle e qualidade na modelagem, foi realizada uma filtragem criteriosa:  
> **Dos 215.257 registros disponíveis, foram selecionados 184.350 registros finais**, sendo **30.907 eliminados por filtros duros.**

---

## 📁 Artefatos do Projeto

A seguir, uma descrição dos principais arquivos e notebooks incluídos neste repositório:

### 📊 Apresentações e Planilhas
- `00_apresentação_vitalis_bank.pptx`  
  👉 Apresentação institucional do projeto e da proposta do modelo

- `00_modelo_de_concessão_de_credito_vitalis_bank.pptx`  
  👉 Pitch de apresentação executiva do modelo de crédito

- `00.metadados_modelos.xlsx`  
  📋 Dicionário com as variáveis utilizadas em cada modelo

- `00.tabelas_metricas_modelos.xlsx`  
  📈 Comparativo das métricas (AUC, Gini, KS) por modelo e versão

---

### 📚 Notebooks do Pipeline de Modelagem

#### 🔎 Exploração e Engenharia de Atributos
- `01_eda_base_modelagem.ipynb`  
  📊 Análise exploratória da base de modelagem

- `02_bureau_balance_feature_engineering.ipynb`  
  🏦 Criação de variáveis a partir da base `bureau_balance`

- `03_bureau_e_application_feature_engineering.ipynb`  
  🔧 Engenharia de variáveis combinando `bureau` e `application`

#### ✂️ Seleção de Variáveis
- `04_feature_selection.ipynb`  
  🧬 Seleção de variáveis com base em métricas de importância

- `05_edas_das_variaveis_selecionadas.ipynb`  
  📊 Análise Bivariada do Target com as variáveis selecionadas

- `06_analise_variaveis_da_edas.ipynb`  
  🔍 Análise de interação entre as variáveis

#### ⚙️ Modelagem e Avaliação
- `07_modelo_xgboost.ipynb`  
  🚀 Treinamento do modelo XGBoost com análise de performance

- `08_modelo_lightgbm.ipynb`  
  🌟 Treinamento do modelo LightGBM com análise de performance - Modelo principal

- `09_matriz_de_migracao.ipynb`  
  📉 Matriz de migração entre os modelos XGBoost e LightGBM

- `10_modelo_lightGBM_sem_scores.ipynb`  
  🧪 Versão do modelo com exclusão dos scores externos

#### 🔁 Análises Incrementais
- `11_analise_incremental_scores_como_variavel.ipynb`  
  🧠 Estudo do ganho de performance com inclusão de cada score externo

- `12_analise_incremental_por_score.ipynb`  
  🔢 Avaliação por camadas de scores (Blend): impacto na AUC e KS

---

## 🧠 Conclusão

Este projeto demonstra como dados públicos e boas práticas de ciência de dados podem ser usados para construir um modelo de concessão de crédito eficiente e escalável. A estrutura modular permite:

- Simulações com diferentes fontes de dados e camadas de score
- Acompanhamento de métricas por versão de modelo
- Apresentações claras e executivas para stakeholders

---

📬 **Entre em contato para colaborações ou sugestões!**

