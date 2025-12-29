# DESAFIO_PROJETO_1


## 🔗 Repositório com Dados, Modelos e Colab

Todo o material complementar do projeto — incluindo **dados utilizados**, **modelos treinados** e uma versão executável em **Google Colab** — está disponível no link abaixo:

👉 **Google Drive (Colab + Dados + Modelos):**
[https://drive.google.com/drive/folders/1pW4c9tk1tH3jqbcfNeRcZqeYd5_Q2X8C?usp=drive_link](https://drive.google.com/drive/folders/1pW4c9tk1tH3jqbcfNeRcZqeYd5_Q2X8C?usp=drive_link)


---

## 📌 Visão Geral

Este projeto tem como objetivo o **desenvolvimento de um modelo de concessão de crédito**, tratando o problema como uma **classificação binária** (aprovado vs. não aprovado). Ele faz parte de um desafio prático voltado para **Ciência de Dados / Machine Learning**, cobrindo desde a análise exploratória até a escoragem do modelo em dados fora do tempo (OOT).

O projeto foi desenvolvido em **Python**, utilizando **Jupyter Notebook**, com foco em boas práticas de modelagem, avaliação e interpretação de resultados.

---

## 📂 Estrutura do Projeto

```
DESAFIO_PROJETO_1/
│
├── Data/
│   ├── train/           
│   ├── test/  
│   ├── oot/
│   ├── csvs/           # Dados pré-processados
│ 
├── Models/
│   ├── model.pkl       # Modelo treinado (exemplo)
├── venv/               # Ambiente virtual Python
│
├── .gitignore          # Arquivos ignorados pelo Git
├── projeto_1.ipynb     # Notebook principal do projeto
├── requirements.txt   # Dependências do projeto
└── README.md           # Documentação do projeto
```

---

## 🧠 Problema de Negócio

Conceder crédito de forma eficiente envolve um **trade-off entre risco e crescimento**. O modelo desenvolvido busca:

* Reduzir inadimplência;
* Maximizar a capacidade de aprovação com risco controlado;
* Apoiar a tomada de decisão através de **score de crédito**.

A saída principal do modelo é um **score** que pode ser convertido em decisão (aprova / não aprova) a partir de um **cut-off**.

---

## ⚙️ Etapas do Projeto

### 1. Entendimento dos Dados

* Análise do dicionário de dados;
* Identificação da variável target;
* Avaliação de períodos temporais (train, test e OOT).

### 2. Análise Exploratória (EDA)

* Distribuição das variáveis;
* Análise de valores nulos e outliers;
* Comportamento temporal da base;
* Análise de desbalanceamento de classes.

### 3. Pré-processamento

* Tratamento de valores nulos;
* Encoding de variáveis categóricas;
* Padronização (quando necessário);
* Separação treino, teste e OOT respeitando o tempo;
* Balanceamento de classes (na base de treino).

### 4. Modelagem

* Treinamento de modelos de classificação;
* Comparação entre abordagens mais **conservadoras** e mais **agressivas**;
* Ajuste de hiperparâmetros;
* Avaliação com métricas adequadas ao negócio.

### 5. Avaliação

Métricas utilizadas:

* Precision
* Recall
* F1-score
* AUC-ROC
* Matriz de confusão

Análise do impacto do **cut-off** na aprovação e no risco.

### 6. Escoragem (Out of Time)

* Aplicação do modelo em dados nunca vistos;
* Conversão do score em decisão de crédito;
* Análise mensal de aprovados vs. não aprovados;
* Avaliação de estabilidade do modelo.

---

## 📊 Exemplo de Regra de Aprovação

```python
base_oot['APROVADO_TO_BE'] = (
    base_oot['score'] >= cutOFF_score
).astype(int)
```

---

## 🛠️ Tecnologias Utilizadas

* Python 3.10+
* Pandas
* NumPy
* Scikit-learn
* LightGBM (ou similar)
* Matplotlib / Plotly
* Jupyter Notebook

---

## 🚀 Como Executar o Projeto

1. Clone o repositório:

```bash
git clone <url-do-repositorio>
cd DESAFIO_PROJETO_1
```

2. Crie e ative o ambiente virtual:

```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\\Scripts\\activate     # Windows
```

3. Instale as dependências:

```bash
pip install -r requirements.txt
```

4. Execute o notebook:

```bash
jupyter notebook projeto_1.ipynb
```

---



## 📄 Observações Finais

Este projeto foi estruturado com foco em **clareza, reprodutibilidade e alinhamento com problemas reais de negócio**, sendo adequado para **portfólio, processos seletivos e estudos acadêmicos**.
