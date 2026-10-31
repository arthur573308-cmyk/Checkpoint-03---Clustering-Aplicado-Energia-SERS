# Checkpoint 3 — Clustering aplicado à energia SERS

## Integrantes
- **Nome:** ARTHUR ARAUJO MASSARIOLI
- **RM:** 573308
- **Turma:** 1CCPK

## Objetivo
Aplicar o algoritmo K-Means para identificar perfis semelhantes de uso de energia entre unidades consumidoras. A atividade utiliza padronização com `StandardScaler`, o método Elbow e o Silhouette Score para apoiar a escolha do número de grupos, além de gráficos e estatísticas para interpretar os perfis.

## Base de dados
O notebook contém a base diretamente em uma célula CSV, portanto não é necessário baixar arquivos externos. São **120 unidades consumidoras fictícias**, geradas previamente para fins didáticos com NumPy e semente 303. Os dados não foram coletados de medidores, empresas ou bases públicas.

Variáveis:
- `id_unidade`: identificador da unidade; não entra no modelo.
- `consumo_mensal_kwh`: consumo total mensal em kWh.
- `demanda_maxima_kw`: maior demanda de potência média em uma janela de 15 minutos no mês, em kW.
- `consumo_noturno_pct`: percentual do consumo mensal entre 18h e 6h.

## Como executar
1. Abra o arquivo `Checkpoint_3_Clustering_Energia_Preenchido.ipynb` no Jupyter Notebook, JupyterLab ou Google Colab.
2. Certifique-se de ter Python 3 e as bibliotecas `pandas`, `numpy`, `matplotlib` e `scikit-learn` instaladas.
3. Execute todas as células na ordem, de cima para baixo.
4. A base já está incorporada ao notebook; não é necessário configurar caminho ou importar CSV externo.

Instalação local das bibliotecas, se necessário:

```bash
pip install pandas numpy matplotlib scikit-learn jupyter
```

## Principais resultados
- Base com **120 registros**, **4 colunas**, nenhum valor ausente e nenhum identificador duplicado.
- As três variáveis numéricas foram padronizadas com `StandardScaler`; o identificador foi excluído do modelo.
- O Elbow apresentou uma queda expressiva da inércia até **k = 3**, seguida por reduções menores.
- O maior Silhouette Score entre k=2 e k=8 foi **0,6031**, também em **k = 3**.
- O modelo final formou três grupos de 40 unidades cada:
  - **Cluster 0:** consumo médio de 876,50 kWh, demanda média de 6,87 kW e consumo noturno médio de 25,49%.
  - **Cluster 1:** consumo médio de 245,09 kWh, demanda média de 2,58 kW e consumo noturno médio de 60,82%.
  - **Cluster 2:** consumo médio de 1.433,93 kWh, demanda média de 6,15 kW e consumo noturno médio de 67,37%.

Os clusters são perfis estatísticos e não classificações de desperdício ou eficiência. A base é simulada e não permite conclusões sobre custos, tarifas ou causas do consumo sem dados adicionais.

## Arquivos
- `Checkpoint_3_Clustering_Energia_Preenchido.ipynb`: notebook executado, com códigos, tabelas, gráficos, análises e conclusão.
- `README.md`: documentação do projeto.
