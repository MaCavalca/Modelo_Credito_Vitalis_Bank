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

## 🔖 Projeto

A seguir, uma descrição dos principais arquivos e notebooks incluídos neste repositório:

### 📊 Apresentações e Planilhas
- `00.apresentacao_vitalis_bank.pdf`  
  👉 Apresentação institucional do projeto e da proposta do modelo
link: https://github.com/MaCavalca/Modelo_Credito_Vitalis_Bank/blob/main/00.apresentacao_modelo_credito_vitalis_bank.pdf

- `00.apresentacao_modelo_credito_vitalis_bank.pdf`  
  👉 Pitch de apresentação executiva do modelo de crédito
link: https://github.com/MaCavalca/Modelo_Credito_Vitalis_Bank/blob/main/00.apresentacao_vitalis_bank.pdf

- `00_metadados_modelos.xlsx`  
  📋 Dicionário com as variáveis utilizadas em cada modelo
link: https://github.com/MaCavalca/Modelo_Credito_Vitalis_Bank/blob/main/00_metadados_modelos.xlsx

- `00_tabelas_metricas_modelos.xlsx`  
  📈 Comparativo das métricas (AUC, Gini, KS) por modelo e versão
link: https://github.com/MaCavalca/Modelo_Credito_Vitalis_Bank/blob/main/00_tabelas_metricas_modelos.xlsx
---

### 📚 Notebooks do Pipeline de Modelagem

#### 🔎 Exploração e Engenharia de Atributos
- `01_eda_base_modelagem.ipynb`  
  📊 Análise exploratória da base de modelagem
link: https://github.com/MaCavalca/Modelo_Credito_Vitalis_Bank/blob/main/01_eda_base_modelagem.ipynb

- `02_bureau_balance_feature_engineering.ipynb`  
  🏦 Criação de variáveis a partir da base `bureau_balance`
link: https://github.com/MaCavalca/Modelo_Credito_Vitalis_Bank/blob/main/02_bureau_balance_feature_engineering.ipynb

- `03_bureau_e_application_feature_engineering.ipynb`  
  🔧 Engenharia de variáveis combinando `bureau` e `application`
link: https://github.com/MaCavalca/Modelo_Credito_Vitalis_Bank/blob/main/03_bureau_e_application_feature_engineering.ipynb

#### ✂️ Seleção de Variáveis
- `04_feature_selection.ipynb`  
  🧬 Seleção de variáveis com base em métricas de importância
link: https://github.com/MaCavalca/Modelo_Credito_Vitalis_Bank/blob/main/04_feature_selection.ipynb

- `05_edas_das_variaveis_selecionadas.ipynb`  
  📊 Análise Bivariada do Target com as variáveis selecionadas
link: https://github.com/MaCavalca/Modelo_Credito_Vitalis_Bank/blob/main/05_edas_das_variaveis_selecionadas.ipynb

- `06_analise_variaveis_da_edas.ipynb`  
  🔍 Análise de interação entre as variáveis
link: https://github.com/MaCavalca/Modelo_Credito_Vitalis_Bank/blob/main/06_analise_variaveis_da_edas.ipynb

#### ⚙️ Modelagem e Avaliação
- `07_modelo_xgboost.ipynb`  
  🚀 Treinamento do modelo XGBoost com análise de performance
link: https://github.com/MaCavalca/Modelo_Credito_Vitalis_Bank/blob/main/07_modelo_xgboost.ipynb

- `08_modelo_lightgbm.ipynb`  
  🌟 Treinamento do modelo LightGBM com análise de performance - Modelo principal
link: https://github.com/MaCavalca/Modelo_Credito_Vitalis_Bank/blob/main/08_modelo_lightgbm.ipynb

- `09_matriz_de_migracao.ipynb`  
  📉 Matriz de migração entre os modelos XGBoost e LightGBM
link: https://github.com/MaCavalca/Modelo_Credito_Vitalis_Bank/blob/main/09_matriz_de_migracao.ipynb

- `10_modelo_lightGBM_sem_scores.ipynb`  
  🧪 Versão do modelo com exclusão dos scores externos
link: https://github.com/MaCavalca/Modelo_Credito_Vitalis_Bank/blob/main/10_modelo_lightgbm_sem_scores.ipynb

#### 🔁 Análises Incrementais
- `11_analise_incremental_scores_como_variavel.ipynb`  
  🧠 Estudo do ganho de performance com inclusão de cada score externo
link: https://github.com/MaCavalca/Modelo_Credito_Vitalis_Bank/blob/main/11_analise_incremental_scores_como_variavel.ipynb

- `12_analise_incremental_por_score.ipynb`  
  🔢 Avaliação por camadas de scores (Blend): impacto na AUC e KS
link: https://github.com/MaCavalca/Modelo_Credito_Vitalis_Bank/blob/main/12_analise_incremental_por_score.ipynb

- 📁 `13_artefatos_modelos.zip`  
  🔢 Pastas com os artefatos gerados pelos modelos
link: [https://github.com/MaCavalca/Modelo_Credito_Vitalis_Bank/blob/main/artefatos_modelos_zip](https://github.com/MaCavalca/Modelo_Credito_Vitalis_Bank/blob/main/artefatos_modelos.zip)
---

## 🧠 Conclusão

Este projeto demonstra como dados públicos e boas práticas de ciência de dados podem ser usados para construir um modelo de concessão de crédito eficiente e escalável. A estrutura modular permite:

- Simulações com diferentes fontes de dados e camadas de score
- Acompanhamento de métricas por versão de modelo
- Apresentações claras e executivas para stakeholders

---

📬 **Entre em contato para colaborações ou sugestões!**

OBS: “Este projeto foi inspirado em boas práticas aprendidas em experiências profissionais, mas todo o conteúdo, código e estrutura são originais e de autoria própria.”

