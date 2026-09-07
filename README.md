# 🤖 Machine Learning & BI: Segmentação de Clientes via Algoritmo K-Means com Python e Power BI

## 📌 Visão Geral do Projeto
Este projeto consiste no desenvolvimento e implementação de um pipeline completo de **Ciência de Dados e Inteligência de Mercado**. O objetivo principal foi solucionar um desafio real de negócios: realizar o agrupamento automatizado (*clustering*) de **500 clientes ativos** por similaridade de comportamento socioeconômico, fornecendo à equipe de Marketing insights preditivos precisos para otimização de campanhas de captação e retenção [0.1.87, cite: 1].

Projeto prático de alta complexidade correspondente ao **Laboratório Prático 7** da formação de Business Intelligence da **Data Science Academy**.

---

## 💼 Desafio de Negócio e Engenharia Preditiva
A diretoria de Marketing demandava um relatório detalhado dividindo a base de consumidores em exatamente **3 segmentos estratégicos**, explicitando para cada grupo a média de idade, renda anual e pontuação de gastos (poder de compra do cliente).

### 📊 Resultados Consolidados do Modelo (Métricas do Dashboard):
Após o processamento e convergência do algoritmo, o ecossistema de dados atingiu as seguintes médias macro [image_BKwJ6q.png]:
* **Total de Clientes Auditados:** 500 [image_BKwJ6q.png]
* **Média de Idade Populacional:** 44,73 anos [image_BKwJ6q.png]
* **Média de Renda Anual Geral:** R\$ 81.557,17 [image_BKwJ6q.png]
* **Média da Pontuação de Gastos (Score):** 48,51 [image_BKwJ6q.png]

### 🔍 Distribuição Volumétrica dos Segmentos (Gráfico de Cascata / Waterfall):
* **Segmento 1 (Perfil Especializado):** 187 clientes mapeados [image_BKwJ6q.png].
* **Segmento 2 (Perfil Moderado):** 167 clientes mapeados [image_BKwJ6q.png].
* **Segmento 0 (Perfil Premium):** 146 clientes mapeados [image_BKwJ6q.png].

---

## 🛠️ Tecnologias, Bibliotecas e Pipelines Utilizados
* **Ambiente de Desenvolvimento:** Jupyter Notebook integrado à distribuição Anaconda3.
* **Linguagem Python (Versão 3.12.3):** Engenharia de código e manipulação de matrizes matemáticas.
* **Pandas:** Carga de arquivos transacionais, análise exploratória descritiva e exportação estruturada (`read_csv` e `to_csv`).
* **Scikit-Learn (Machine Learning):**
  * `StandardScaler`: Normalização e padronização vetorial das escalas numéricas para mitigar distorções de magnitude entre Renda e Idade.
  * `KMeans(n_clusters=3)`: Treinamento e ajuste do algoritmo de agrupamento de centroides.
* **Microsoft Power BI:** Arquitetura dimensional do painel e integração do arquivo `segmentos.csv` para renderização visual das métricas de IA.

---

## 💻 Arquitetura do Código de Machine Learning

```python
# Importação das bibliotecas especializadas
import pandas as pd
from sklearn.cluster import KMeans
from sklearn.preprocessing import StandardScaler

# Carga da base de dados transacional limpa
df_dsa = pd.read_csv('dados/dados_clientes.csv')

# Aplicação do padronizador de escala para tratamento estatístico
padronizador = StandardScaler()
dados_padronizados = padronizador.fit_transform(df_dsa[['idade', 'renda_anual', 'pontuacao_gastos']])

# Configuração e treinamento do modelo de Inteligência Artificial (K-Means)
k = 3
kmeans = KMeans(n_clusters = k)
kmeans.fit(dados_padronizados)

# Atribuição das classes/rótulos preditivos na base oficial
df_dsa['cluster'] = kmeans.labels_

# Exportação do resultado higienizado para a camada de Business Intelligence
df_dsa.to_csv('dados/segmentos.csv', index = False)
```

---

## 📂 Organização dos Arquivos no Repositório
* `dados/dados_clientes.csv`: Base de dados transacional bruta com os registros individuais.
* `dados/segmentos.csv`: Base de dados de saída enriquecida com a coluna preditiva de `cluster` calculada pela IA.
* `Lab7_Machine_Learning.ipynb`: Notebook Jupyter contendo a engenharia e execução do código Python.
* `Dashboard_Segmentacao.pbix`: Relatório interativo final do Power BI consumindo os dados gerados pelo modelo.
* `README.md`: Documentação técnica e científica do projeto.

---

## 👤 Autor
* **Eduardo Cruz**
* LinkedIn: [eduardo-cruz777](https://linkedin.com)
* Email: edufracruz@gmail.com
<img width="1366" height="768" alt="dados" src="https://github.com/user-attachments/assets/e8031fff-56da-4841-b8a9-b7ab34743c9b" />
<img width="986" height="553" alt="dashboard_13b" src="https://github.com/user-attachments/assets/1f492f43-26dd-41f2-959a-62dae58274a7" />
<img width="911" height="551" alt="dashboard_13a" src="https://github.com/user-attachments/assets/977b31f5-bed9-405a-bfb4-baaa919240dc" />
