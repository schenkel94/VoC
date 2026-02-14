# VOC Classificacao 2025

Este repositório contém um notebook para classificar mensagens de VOC (Voice of Customer) com:

- **sentimentalidade**: POSITIVA, NEUTRA, NEGATIVA
- **categoria**: rótulos determinísticos (por palavras-chave) como INSTABILIDADE NA PLATAFORMA, API/AUTENTICACAO, SUPORTE/ATENDIMENTO, FINANCEIRO, TREINAMENTO/ONBOARDING, FEATURE REQUEST etc.

## Arquivos

- `voc_classificacao.ipynb`: notebook principal
- `voc_silver_2025.csv`: entrada esperada (não incluído aqui, você fornece)
- `voc_gold_2025.csv`: saída gerada pelo notebook

## Como rodar

1. Coloque o arquivo `voc_silver_2025.csv` na mesma pasta do notebook.
2. Abra `voc_classificacao.ipynb` no Jupyter/VS Code/Colab.
3. Execute as células em ordem.
4. Ao final, será gerado `voc_gold_2025.csv`.

## Observações sobre o modelo de sentimento

O notebook tenta usar um modelo gratuito/local do Hugging Face (`cardiffnlp/twitter-xlm-roberta-base-sentiment`).

Se o ambiente não conseguir baixar/usar o modelo, ele cai automaticamente em um **fallback por regras** (palavras-chave) para sentimento.

## Colunas esperadas no CSV de entrada

O `voc_silver_2025.csv` deve conter (no mínimo) as colunas:

- `data`
- `origem`
- `usuario`
- `mensagem`

Caso existam colunas extras, elas serão preservadas.
