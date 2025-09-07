# Análise Exploratória de Dados de Logística da Loggi no Distrito Federal

![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg)
![Libraries](https://img.shields.io/badge/Libraries-Pandas%20%7C%20GeoPandas%20%7C%20Seaborn-orange.svg)
![Data Format](https://img.shields.io/badge/Data-JSON-yellow.svg)

---

## 🎯 1. Visão Geral do Projeto

Este projeto consiste numa **Análise Exploratória de Dados (EDA)** focada nas operações logísticas da empresa **Loggi** no Distrito Federal. Utilizando um conjunto de dados em formato JSON, que descreve instâncias de entrega, hubs de distribuição e as respetivas coordenadas geográficas, esta análise visa desvendar padrões e otimizar a eficiência das rotas.

O principal objetivo é transformar dados brutos e aninhados num formato estruturado, enriquecê-los com informações geoespaciais e gerar insights visuais através de mapas, identificando a distribuição das entregas e a concentração de operações por região.

---

## 🗺️ 2. Visualização Principal: Mapa de Entregas por Hub

Um dos principais resultados da análise é a visualização geoespacial que demonstra a concentração de entregas para cada um dos três hubs de distribuição (df-0, df-1 e df-2) no mapa do Distrito Federal.

<img width="1920" height="1008" alt="Captura de tela 2025-09-07 190625" src="https://github.com/user-attachments/assets/69d6fba9-7202-45dc-866c-2eb6f99013df" />


---

## 📂 3. Fonte e Estrutura dos Dados

Os dados foram fornecidos num ficheiro `deliveries.json`, contendo uma lista de instâncias de entrega com a seguinte estrutura aninhada:

* **name**: Nome único da instância.
* **region**: Região do hub de distribuição.
* **origin**: Dicionário com `lat` e `lng` do hub.
* **vehicle_capacity**: Capacidade de carga dos veículos do hub.
* **deliveries**: Lista de dicionários, cada um representando uma entrega com `id`, `point` (coordenadas) e `size` (tamanho).

---

## ✨ 4. Metodologia e Análises Realizadas

O notebook documenta um processo completo de *data wrangling* e análise, incluindo as seguintes etapas:

1.  **Manipulação de Dados (Data Wrangling):**
    * **Flattening & Exploding:** Foi realizada a normalização dos dados JSON aninhados. As informações de `origin` foram achatadas (`flatten`) e a lista de `deliveries` foi "explodida" (`explode`) para transformar cada entrega individual numa linha única do DataFrame, facilitando a análise.

2.  **Enriquecimento Geoespacial (Geocodificação Reversa):**
    * Utilizando a biblioteca `geopy`, as coordenadas de latitude e longitude dos hubs de distribuição foram convertidas em informações de endereço (cidade e bairro) através da geocodificação reversa.
    * Um processo similar foi aplicado às coordenadas de entrega, enriquecendo o dataset principal com a localização textual de cada ponto.

3.  **Análise Exploratória e Visualização:**
    * **Distribuição de Entregas:** Análise da proporção de entregas por região, identificando a concentração da demanda.
    * **Visualização Geográfica:** Utilização do `geopandas` e `matplotlib` para plotar os hubs e os pontos de entrega sobre o mapa do Distrito Federal, proporcionando insights visuais imediatos sobre a dispersão geográfica das operações.

---

## 💡 5. Principais Insights Gerados

* **Concentração de Demanda:** A análise revelou que as entregas estão fortemente concentradas nos hubs das regiões **df-1 (48%)** e **df-2 (41%)**, enquanto o hub da região **df-0** responde por apenas **11%** da demanda.
* **Oportunidade de Otimização:** Apesar da disparidade na demanda, a capacidade dos veículos é idêntica em todos os hubs. Isto sugere uma oportunidade de otimizar a alocação de recursos, possivelmente deslocando veículos da região 0 para as regiões de maior tráfego.
* **Desafios Operacionais da Região 0:** Embora com menor volume, as entregas do hub da região 0 tendem a ser mais distantes e geograficamente dispersas, o que pode impactar negativamente o tempo e o custo de entrega.

---

## 🛠️ 6. Ferramentas e Tecnologias

* **Linguagem:** Python
* **Bibliotecas:** `pandas`, `geopy`, `geopandas`, `matplotlib`, `seaborn`
* **Ambiente:** Jupyter Notebook (Google Colab)

---

## 🚀 7. Como Executar o Projeto

1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/](https://github.com/)[seu-usuario]/[nome-do-repositorio].git
    ```
2.  **Instale as dependências:**
    ```bash
    pip install pandas geopy geopandas matplotlib seaborn
    ```
3.  **Execute o Notebook:**
    Abra o ficheiro `.ipynb` no Jupyter Notebook ou Google Colab. O código fará o download dos dados necessários e executará toda a análise.

---

## 👨‍💻 8. Autor

* **Higor Silva**
* **LinkedIn:** https://www.linkedin.com/in/higor-silva-4a7341273/
