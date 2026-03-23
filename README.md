# 📊 Voice of Customer (VOC) 2025: NLP & Analytics Pipeline

![Status](https://img.shields.io/badge/Status-Conclu%C3%ADdo-brightgreen)
![Python](https://img.shields.io/badge/Python-3.9+-blue)
![Power BI](https://img.shields.io/badge/Visualiza%C3%A7%C3%A3o-Power%20BI-yellow)
![Hugging Face](https://img.shields.io/badge/IA-Hugging%20Face-orange)

Este repositório contém uma solução completa de **Engenharia de Dados e NLP** para classificar e analisar feedbacks de clientes (Voice of Customer). O projeto transforma dados brutos em insights estratégicos através de um pipeline que automatiza a identificação de sentimentos e categorias críticas de negócio.

## 📈 Dashboard Interativo
Clique na imagem abaixo para abrir a [versão interativa no Power BI](https://app.powerbi.com/view?r=eyJrIjoiYTU4MDhlOTAtOWZkOC00ZjQwLThiZjUtMWNiZGEwOTcyYTM2IiwidCI6ImE2Yjc2OWVmLTlmN2MtNDcxZS04Y2Q2LWNjYTBiNzE4YmJmZSJ9) e explorar os indicadores:

[![Dashboard VOC](https://raw.githubusercontent.com/schenkel94/VoC/main/VOC.png)](https://app.powerbi.com/view?r=eyJrIjoiYTU4MDhlOTAtOWZkOC00ZjQwLThiZjUtMWNiZGEwOTcyYTM2IiwidCI6ImE2Yjc2OWVmLTlmN2MtNDcxZS04Y2Q2LWNjYTBiNzE4YmJmZSJ9)
*Preview do dashboard desenvolvido para monitoramento de KPIs de satisfação.*

---

## 🧠 Inteligência do Projeto (Python Pipeline)

O processamento principal é realizado no arquivo [`notebook_voc.ipynb`](https://github.com/schenkel94/VoC/blob/main/notebook_voc.ipynb), que executa as seguintes etapas técnicas:

### 1. Classificação de Sentimentos com IA
* **Modelo**: Utilizamos o modelo de Deep Learning **`cardiffnlp/twitter-xlm-roberta-base-sentiment`** da Hugging Face para análise multilíngue.
* **Sistema de Resiliência**: O script inclui uma lógica de **fallback por regras** (baseada em léxicos de palavras-chave) que assume o processamento caso o modelo de IA não possa ser carregado no ambiente, garantindo a continuidade do pipeline.
* **Labels**: As mensagens são classificadas como `POSITIVA`, `NEUTRA` ou `NEGATIVA`.

### 2. Categorização Automática
Implementamos um motor de regras determinístico para agrupar feedbacks em categorias estratégicas:
* **Operacional**: Instabilidade na Plataforma, API/Autenticação, Bugs.
* **Relacionamento**: Suporte/Atendimento, Treinamento/Onboarding.
* **Negócio**: Financeiro, Feature Request.

---

## 🛠️ Tecnologias e Ferramentas

* **Linguagem**: Python (Pandas, Numpy)
* **Machine Learning**: Transformers (Hugging Face), PyTorch
* **Infraestrutura**: Databricks / Unity Catalog Volumes
* **BI**: Power BI Service

---

## 📂 Estrutura de Arquivos

* [`notebook_voc.ipynb`](https://github.com/schenkel94/VoC/blob/main/notebook_voc.ipynb): Core do projeto; realiza a limpeza, classificação e exportação dos dados.
* `voc_gold_2025.csv`: Base de dados de entrada com os feedbacks brutos.
* `voc_gold_processed_2025.csv`: Base de dados final, enriquecida com sentimento e categoria, consumida pelo Power BI.
* [`VOC.png`](https://github.com/schenkel94/VoC/blob/main/VOC.png): Imagem de capa do dashboard para visualização neste repositório.

---

## 🚀 Como Executar

1. **Instalar Dependências**:
   ```bash
   pip install transformers torch tqdm pandas
2. **Preparar Dados**: Certifique-se de que o arquivo de entrada (`voc_gold_2025.csv`) está no caminho configurado no notebook.
3. **Processar**: Execute as células do [`notebook_voc.ipynb`](https://github.com/schenkel94/VoC/blob/main/notebook_voc.ipynb) para gerar o arquivo processado final.

---

## 👤 Autor
**Mário Schenkel** – Business Data Analyst
* [Meu Portfólio](https://schenkel94.github.io/portfolio/)
* [LinkedIn](https://www.linkedin.com/in/marioschenkel/)
