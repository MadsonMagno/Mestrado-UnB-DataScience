# Repositório de Modelagem: Priorização de Vulnerabilidades (Acórdão 1889/2020 TCU)

Este repositório contém toda a pipeline técnica desenvolvida para a dissertação de mestrado, provando a eficácia da clusterização (K-Means e DBSCAN) combinada com inteligência de ameaças (EPSS) para priorização institucional de riscos cibernéticos governamentais.

## Arquitetura do Projeto

O fluxo de processamento e validação acadêmica está dividido de forma linear nas seguintes fases:

### 1. FASE_1_INTELIGENCIA_REAL (Enriquecimento)
A partir de vulnerabilidades detectadas, este módulo enriquece os dados puros com o score **EPSS** e aplica o cálculo ponderado baseado no Acórdão TCU (NCS, PPSI, Impacto). Gera o "Ground Truth" (dataset de benchmarks) para o projeto.

### 2. FASE_2_MODELAGEM_REAL (Clustering Aplicado)
*(Pasta original: FASE_3_MODELAGEM_CLUSTERING)*
Submete os dados enriquecidos a um processo de Machine Learning (K-Means). Utilizamos o Método do Cotovelo para justificar matematicamente a divisão em 5 clusters, alinhando a densidade dos dados com os 5 níveis de risco exigidos pelo TCU (Mínimo a Crítico).

### 3. FASE_3_VALIDACAO_SINTETICA (Stress Test)
*(Pasta original: FASE_2_STRESS_TEST_SINTETICO)*
Para provar a escalabilidade matemática e mitigação de viés (Bias Mitigation), utilizamos Inteligência Artificial Generativa (SDV / CTGAN) treinada sobre os dados reais para gerar mais de 100.000 vulnerabilidades sintéticas com altíssima Fidelidade. Em seguida, injetamos **Edge Cases** (anomalias extremas) propositais. O DBSCAN atua como filtro de ruído e o K-Means processa a massa total sem quebra de estrutura, provando a estabilidade da taxonomia (Synthetic Trust).

### 4. FASE_4_RELATORIO_ESTATISTICO (Consolidação)
Geração das estatísticas consolidadas finais, gráficos comparativos de altíssima resolução e relatórios analíticos de eficiência (Mundo Real vs Mundo Sintético) para exportação direta ao texto final da dissertação.

## Requisitos
- Python 3.10+
- Pandas, Numpy, Scikit-Learn, Seaborn
- SDV (Synthetic Data Vault) - Para treinamento da IA generativa.
