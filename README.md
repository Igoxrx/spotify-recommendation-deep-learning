# 🎵 Spotify Audio Features - Genre Prediction (Deep Learning & Multilabel)

Este projeto aplica técnicas avançadas de Ciência de Dados e Inteligência Artificial para classificar e prever gêneros musicais com base em atributos técnicos de áudio das faixas do Spotify (como *acousticness*, *danceability*, *energy*, *tempo*, entre outros).

O principal diferencial do projeto é a abordagem de **Classificação Multilabel**, mapeando cenários reais onde uma única música pode pertencer a múltiplos gêneros simultaneamente.

---

## 🛠️ Tecnologias e Ferramentas Utilizadas

*   **Linguagem:** Python
*   **Manipulação e Análise de Dados:** Pandas, NumPy
*   **Visualização:** Matplotlib, Seaborn
*   **Machine Learning (Baseline):** Scikit-Learn (Random Forest Classifier, MultiOutputClassifier)
*   **Deep Learning (IA):** TensorFlow / Keras (Modelos Sequenciais, Otimizador Adam, Early Stopping)

---

## 📈 Estrutura do Pipeline de Dados

1.  **Limpeza e Pré-processamento:**
    *   Remoção e tratamento de registros duplicados (`track_id`).
    *   Filtração de variáveis não utilizáveis para o modelo (`artist_name`, `track_name`).
    *   Codificação de variáveis categóricas de teoria musical (`key` e `mode`) para formato numérico.
    *   Reorganização e agrupamento de classes e gêneros musicais semelhantes.
2.  **Abordagem Multilabel:**
    *   Utilização do `MultiLabelBinarizer` para agrupar múltiplos gêneros associados à mesma faixa.
    *   Normalização dos dados com `StandardScaler` para otimizar o gradiente das Redes Neurais.

---

## 🤖 Modelos Implementados e Resultados

### 1. Random Forest Classifier (Machine Learning Clássico)
*   Implementado como primeiro modelo de teste para classificação multiclasse e multilabel (com `MultiOutputClassifier`).
*   **Métricas avaliadas:** Perda de Hamming (Hamming Loss), Pontuação Jaccard e Matrizes de Confusão por classe para análise de falso-positivos.

### 2. Rede Neural Profunda / Multi-Layer Perceptron (TensorFlow/Keras)
*   Construção de uma arquitetura de rede neural sequencial densa com camadas de `Dropout` para evitar *overfitting*.
*   Uso de função de ativação `sigmoid` na camada de saída combinada com perda de entropia cruzada binária suavizada (`BinaryCrossentropy(label_smoothing=0.1)`) para predições multilabel eficientes.
*   **Otimização de Thresholds:** Implementação de curvas de Precisão x Recall (`precision_recall_curve`) por classe para encontrar o limiar matemático perfeito e maximizar o F1-Score do modelo.

---

## 📊 Como Visualizar os Resultados

O script gera automaticamente gráficos essenciais para análise de performance:
*   **Matriz de Correlação de Gêneros Musicais:** Entendimento visual de quais gêneros costumam coexistir nas faixas.
*   **Curvas de Aprendizado (Loss e Acurácia):** Gráficos comparativos entre os dados de Treino e Validação ao longo das épocas para auditar o aprendizado da IA.
*   **Relatório de Classificação:** Métricas detalhadas de Precisão, Recall e F1-Score por classe.

---

## 🚀 Como Executar o Projeto

1. Clone o repositório:
```bash
   git clone [https://github.com/SEU_USUARIO/NOME_DO_REPOSITORIO.git](https://github.com/SEU_USUARIO/NOME_DO_REPOSITORIO.git)
