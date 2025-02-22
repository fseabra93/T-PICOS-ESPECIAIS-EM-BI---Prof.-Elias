# TÓPICOS-ESPECIAIS-EM-BI---Prof.-Elias
Trabalho entregue para a disciplina de IMD0190 - TÓPICOS ESPECIAIS EM BUSINESS INTELIGENCE E ANALYTICS - T03 (2024.2), Prof. ELIAS JACOB DE MENEZES NETO


# Modelo Preditivo de Afastamentos por Motivo de Saúde - TRE-RN

Este projeto visa desenvolver um modelo preditivo de afastamentos por motivo de saúde, analisando padrões e tendências nos afastamentos médicos dos servidores do TRE-RN.

## Visão Geral

O projeto utiliza um conjunto de dados históricos de 2000 a 2023, coletados de diferentes fontes para construir modelos de machine learning capazes de prever a duração dos afastamentos.

## Fontes de Dados

1.  **Módulo Afastamentos do SGRH:** Dados de afastamentos por motivo de saúde (LICENÇA PARA TRATAMENTO DA PRÓPRIA SAÚDE, LICENÇA POR DOENÇA EM PESSOA DA FAMÍLIA, LICENÇA POR ACIDENTE EM SERVIÇO e LICENÇA À GESTANTE) de 2000 a 2023, incluindo o CID.
2.  **Módulo Gestão do SGRH:** Dados de cada servidor, como data de nascimento (para extrair a idade), data da posse (para extrair o tempo de serviço), sexo, identidade de gênero, raça/cor da pele e informações sobre aprovação em regime de cotas.
3.  **Portal de Dados Abertos do TRE-RN:** Dados de cada servidor, como lotação (Sede ou Zonas Eleitorais), nível de escolaridade (Intermediário ou Superior), cargo, área, situação e informações sobre comissão (se o servidor recebe alguma função comissionada ou não).

## Pré-Processamento

*   Servidores sem dados no Portal de Dados Abertos foram removidos do conjunto de dados.
*   Dados de identificação foram removidos.
*   Códigos CID foram simplificados para a letra correspondente à classe de doenças.
*   One-Hot Encoding foi aplicado a diversas variáveis categóricas.
*   Uma variável 'Classe' foi criada para classificar os afastamentos em curta duração (até 2 dias) e longa duração (a partir de 3 dias).

## Modelagem

O projeto explora dois modelos de machine learning para prever a duração dos afastamentos:

1.  **MLP (Multi-Layer Perceptron):** Uma rede neural feedforward.
2.  **LSTM (Long Short-Term Memory):** Uma rede neural recorrente adequada para dados sequenciais.

## Arquivos

*   `licencas_medicas_Disc_topicos.ipynb`: Notebook Jupyter com o código completo do projeto.
*   `df_afastamentos_para_Topicos.csv`: Dataset pré-processado utilizado no notebook.
*   `README.md`: Este arquivo, contendo a documentação do projeto.

## Como usar

1.  **Instalação:** Certifique-se de ter o Python 3 instalado. Instale as seguintes bibliotecas:

    ```bash
    pip install pandas scikit-learn matplotlib torch
    ```

2.  **Execução:** Execute o notebook `licencas_medicas_Disc_topicos.ipynb` em um ambiente Jupyter.
    *   Certifique-se de que o arquivo `df_afastamentos_para_Topicos.csv` esteja no mesmo diretório do notebook.
    *   Execute as células em ordem para reproduzir os resultados.

## Estrutura do Código

O notebook está dividido em seções:

*   **Carregamento de Dados:** Carrega o dataset pré-processado.
*   **Análise usando MLP:** Implementa e avalia o modelo MLP.
*   **Análise usando LSTM:** Implementa e avalia o modelo LSTM.

## Autores

*   ELIKAH DE SANTANA E FRANCA SANTHIAGO
*   FLÁVIO ROBERTO GUERRA SEABRA
*   SANDERSON LELIS DE MACEDO COSTA
