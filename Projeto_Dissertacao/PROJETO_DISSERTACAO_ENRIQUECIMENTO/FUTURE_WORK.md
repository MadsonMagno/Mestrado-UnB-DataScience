# Ideias de Projetos Futuros e Expansão

Durante o planejamento da dissertação (Maio de 2026), foi identificada a oportunidade de criar um produto derivado desta pesquisa, possivelmente útil para defesas em Mestrados Profissionais ou aplicações práticas no governo.

## Produto Tecnológico: Dashboard de Priorização (TCU + EPSS)

### Conceito
Construir uma ferramenta interativa (WebApp) que empacote o algoritmo K-Means validado nesta dissertação em uma interface amigável para auditores e gestores de TI governamentais.

### Fluxo de Uso
1. **Upload:** O gestor de segurança sobe um arquivo padrão gerado por scanners de mercado (ex: ZAP Report, Qualys, Nessus).
2. **Enriquecimento Automático:** A ferramenta consulta a API do EPSS em tempo real (ou via cache local) para atualizar o *Threat Intelligence*.
3. **Clusterização em Tempo Real:** O pipeline de Machine Learning aplica o cálculo da métrica TCU (NCS, Impacto, PPSI) e joga a base no modelo treinado de K-Means.
4. **Visualização Prática:** O Dashboard (que pode ser construído em `Streamlit` ou `FastAPI + React`) exibe gráficos de funil dinâmicos e exporta um relatório executivo segmentando imediatamente quais vulnerabilidades exigem resposta imediata ("Nível Crítico" - Cluster 4) e quais são apenas falsos positivos técnicos.

### Por que deixamos para depois?
O escopo principal da dissertação foca na **validação metodológica** (provando matematicamente através de dados reais e sintéticos que o modelo funciona). A camada de interface visual não é estritamente necessária para a defesa acadêmica atual, mas serve como um poderoso "Trabalho Futuro" na conclusão do texto.
