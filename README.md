# Luiz Fernando MG Consultoria

## Overview

Este repositório contém parte  do projeto desenvolvido para análise de empresas importadoras de cobre no estado de Minas Gerais, com foco nas importações realizadas no ano de 2020. O objetivo principal deste projeto é identificar as top 10 empresas importadoras de cobre, de acordo com o volume importado e valor FOB, e apresentar uma lista consistente e qualificada para fins de análise e prospecção de negócios.

## Conteúdo do Repositório

O repositório está organizado com os seguintes notebooks e arquivos:

### 1. **`dados_empresas_importadoras_cobre.csv`**
- Contém os dados brutos das empresas importadoras de cobre extraídos diretamente via consulta SQL no Google BigQuery, utilizando a base de dados pública do **Base dos Dados**.
- Inclui informações sobre o CNPJ, razão social, município de operação, peso e valor FOB das importações realizadas.

### 2. **`consulta_dados_basedosdados.ipynb`**
- Notebook utilizado para a conexão com o BigQuery e a extração dos dados a partir da base `basedosdados.br_me_comex_stat.ncm_importacao` e `basedosdados.br_me_exportadoras_importadoras.estabelecimentos`.
- Implementa filtros para considerar apenas as empresas ativas no ano de 2020, excluindo Microempreendedores Individuais (MEIs) e empresas inativas.
- Faz o tratamento inicial dos dados e salva o arquivo `dados_empresas_importadoras_cobre.csv` para uso no próximo notebook.

### 3. **`analise_dados_empresas_importadoras.ipynb`**
- Notebook responsável por carregar o arquivo CSV gerado na etapa anterior e realizar a análise exploratória dos dados.
- Implementa uma série de verificações de consistência para assegurar a qualidade dos dados, como validações de valores de peso e valor FOB das importações.
- Gera um ranking das 10 maiores empresas importadoras de cobre em Minas Gerais no ano de 2020, baseado no valor FOB ajustado.
- Salva os resultados finais para referência e documentação.

## Metodologia

A análise foi conduzida com as seguintes etapas:

1. **Coleta dos Dados**:
   - Extração dos dados de importação de cobre para o estado de Minas Gerais no ano de 2020.
   - Utilização das colunas de CNPJ, razão social, município, peso líquido em KG e valor FOB em dólar.

2. **Filtragem e Limpeza**:
   - Remoção de empresas inativas e Microempreendedores Individuais (MEIs).
   - Agrupamento dos dados por município para calcular o total de importações por região e empresa.

3. **Cálculo da Proporção de Importação por Empresa**:
   - Cálculo do peso e valor FOB proporcional por empresa, considerando o número total de empresas por município.
   - Identificação das inconsistências nos dados e ajustes manuais para garantir a acuracidade dos resultados.

4. **Ranking Final**:
   - Definição do top 10 das maiores empresas importadoras de cobre de MG para 2020.
   - Exportação dos resultados para um arquivo `.csv` e visualização dos resultados no notebook.

## Requisitos

- Python 3.8+
- Bibliotecas:
  - `pandas`
  - `basedosdados`
  - `matplotlib`
  - `numpy`
- Permissões de acesso ao Google BigQuery, utilizando o projeto `mindful-syntax-425913-g9`.

## Execução

Para replicar os resultados, siga os seguintes passos:

1. Clone o repositório:
   ```bash
   git clone https://github.com/<seu-usuario>/luiz-fernando-mg-consultoria.git

2. Instale as dependências necessárias
   ```bash
   pip install pandas basedosdados matplotlib numpy

3. Acesse o notebook ```consulta_dados_basedosdados.ipynb``` para extrair os dados do BigQuery e salvar o CSV.
4. Carregue o notebook ```analise_dados_empresas_importadoras.ipynb``` e execute as células para obter a análise final.

## Resultados Finais

O arquivo final gerado é o ```top10_empresas_importadoras_cobre_2020.csv```, contendo as seguintes colunas:
* CNPJ: Identificador único da empresa.
* Razão Social: Nome da empresa.
* Município: Localização da empresa no estado de Minas Gerais.
* Peso Cobre Ajustado (kg): Quantidade de cobre importada ajustada proporcionalmente.
* Valor FOB Ajustado (USD): Valor FOB ajustado proporcionalmente.

## Autor
Desenvolvido por Luiz Fernando MG Consultoria. Se precisar de mais detalhes ou desejar aplicar esta metodologia para outros estados ou setores, entre em contato!



