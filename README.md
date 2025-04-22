# Monitoramento de Modelos - Data Drift Detection

Este projeto tem como objetivo **monitorar modelos de Machine Learning em produção**, com foco especial na **detecção de Data Drift** – mudanças nas distribuições dos dados ao longo do tempo, que podem comprometer a performance preditiva de modelos já treinados.

---

## Visão Geral

Com o tempo, os dados que alimentam um modelo podem mudar devido a fatores externos como comportamento de usuários, sazonalidade, eventos econômicos ou mudanças de sistema. Esse fenômeno é conhecido como **Data Drift**.

Este notebook simula um ambiente de produção e implementa técnicas estatísticas para:

- Comparar os dados de produção com os dados originais de treinamento.
- Identificar mudanças significativas na distribuição das variáveis.
- Gerar visualizações que facilitam a tomada de decisão sobre reentreinar ou ajustar o modelo.

---

## ⚙️ Tecnologias e Bibliotecas Utilizadas

- **Python 3.10+**
- **Pandas** – Manipulação de dados tabulares
- **Numpy** – Operações numéricas
- **Matplotlib** e **Seaborn** – Visualização de dados
- **Scipy** – Testes estatísticos (KS Test)
- **Scikit-learn** – Pré-processamento e utilidades
- **PSI (Population Stability Index)** – Implementado para medir a estabilidade da distribuição

---

## Metodologia

1. **Simulação dos Dados**:
   - Geração de um conjunto de dados base (treinamento).
   - Simulação de dados de produção com pequenas alterações nas distribuições.

2. **Análise Estatística**:
   - **KS Test** (Kolmogorov–Smirnov): verifica se duas distribuições são estatisticamente diferentes.
   - **PSI (Population Stability Index)**: quantifica a mudança na distribuição das variáveis.

3. **Visualização**:
   - Histogramas e KDEs comparando a distribuição das variáveis no tempo.
   - Dashboard simples em notebook para acompanhamento manual.

---

## Resultados

- Foi possível detectar alterações significativas em variáveis simuladas como "idade" e "renda".
- O PSI identificou desvios sutis que o KS Test não capturava isoladamente.
- Gráficos facilitaram a interpretação das mudanças e ajudaram na tomada de decisão quanto à manutenção do modelo.

---

## Possíveis Extensões

- Automatização em pipelines de MLOps.
- Alertas em tempo real com dashboards (ex: Streamlit, Dash).
- Integração com modelos preditivos já em produção.

---

## 📎 Como Executar

1. Clone o repositório:
   ```bash
   git clone https://github.com/flaviohenriquehb777/Projeto_Monitoramento_Modelo_Data_Drift.git
   cd monitoramento-data-drift
