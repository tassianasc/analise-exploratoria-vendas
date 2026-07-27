# Análise Exploratória de Dados de Vendas

<p align="center">
  <img alt="Python" src="https://img.shields.io/badge/Python-EDA-blue?style=for-the-badge&logo=python" />
  <img alt="Google Colab" src="https://img.shields.io/badge/Google%20Colab-Notebook-orange?style=for-the-badge&logo=googlecolab" />
  <img alt="Pandas" src="https://img.shields.io/badge/Pandas-Tratamento%20de%20Dados-150458?style=for-the-badge&logo=pandas" />
  <img alt="Matplotlib" src="https://img.shields.io/badge/Matplotlib-Visualiza%C3%A7%C3%A3o-green?style=for-the-badge" />
  <img alt="Seaborn" src="https://img.shields.io/badge/Seaborn-Estilo%20Gr%C3%A1fico-4C72B0?style=for-the-badge" />
</p>

Projeto desenvolvido na atividade **PY-06** com foco em **Análise Exploratória de Dados (EDA)** usando Python no **Google Colab**. O notebook investiga um conjunto de dados de vendas, realiza limpeza e enriquecimento da base, constrói análises descritivas e apresenta visualizações para apoiar a interpretação dos resultados.

***

## Visão geral

Este projeto tem como finalidade analisar o comportamento das vendas em diferentes dimensões do conjunto de dados, com destaque para:

- desempenho por **dia da semana**;
- resumo de vendas por **região**;
- relação entre **custo, venda e lucro**;
- criação de novos atributos para apoiar a leitura analítica;
- interpretação dos resultados com recomendações práticas.

Além da parte técnica, o projeto também foi estruturado para servir como material de estudo, com células organizadas, comentários explicativos e etapas progressivas de exploração dos dados.

***

## Objetivo do projeto

O objetivo principal é aplicar técnicas introdutórias de EDA para transformar dados brutos de vendas em informações mais claras e úteis para tomada de decisão. Durante a análise, o notebook busca responder perguntas como:

- Como as vendas se distribuem ao longo da semana?
- Quais regiões concentram maior volume de vendas?
- Qual é a relação entre custo, venda e lucro?
- Existem padrões iniciais que possam orientar ações comerciais?

A proposta também desenvolve habilidades práticas com `pandas`, `numpy`, `matplotlib` e `seaborn`, reforçando a leitura, transformação, agregação e visualização de dados em Python.

***

## Conjunto de dados

**Nome do arquivo principal:** `sales_data.csv`

**Origem do conjunto de dados:** arquivo CSV utilizado na atividade prática do notebook no Google Colab.

### Colunas principais utilizadas

| Coluna | Descrição |
|--------|-----------|
| `Sales` | Valor da `venda` realizada. |
| `Region` | Região associada ao registro de venda. |
| `Product` | Produto relacionado à venda. |
| `Date` | Data do registro. |
| `Cost` | Custo associado à venda. |

### Atributos criados durante a análise

| Novo atributo | Finalidade |
|---------------|------------|
| `Month` | Identificar o mês da venda. |
| `Day_of_Week` | Analisar vendas por dia da semana. |
| `Profit` | Calcular o lucro por registro (`Sales - Cost`). |
| `Margin_Percent` | Medir a margem percentual da venda. |
| `Sales_Normalized` | Normalizar os valores de venda. |
| `Sales_Tier` | Classificar vendas em categorias como `Alta` e `Baixa`. |

***

## Estrutura dos arquivos

```text
.
├── PY-06_EDA_Vendas_Colab.ipynb
├── sales_data.csv
├── sales_data_analisado.csv
└── README.md
```

### Descrição dos arquivos

- `PY-06_EDA_Vendas_Colab.ipynb`: notebook principal com importação, tratamento, análise e visualização dos dados.
- `sales_data.csv`: base original utilizada durante a atividade.
- `sales_data_analisado.csv`: base exportada ao final com os novos atributos gerados.
- `README.md`: documentação do projeto.

***

## Bibliotecas utilizadas

As bibliotecas empregadas no notebook foram:

```python
import io
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
from google.colab import files
```

### Papel de cada biblioteca

- **io**: leitura do arquivo enviado no ambiente do Colab.
- **NumPy**: apoio em cálculos numéricos e criação de colunas derivadas.
- **Pandas**: carregamento, inspeção, transformação e agregação dos dados.
- **Matplotlib**: construção de gráficos base.
- **Seaborn**: refinamento visual e gráficos estatísticos.
- **google.colab.files**: upload do CSV e download do arquivo final analisado.

***

## Etapas da análise

O notebook foi organizado em uma sequência didática, passando pelas seguintes fases:

### 1. Preparação do ambiente

- importação das bibliotecas;
- configuração visual do Seaborn;
- ajuste das opções de exibição do Pandas.

### 2. Carregamento do arquivo CSV

- upload manual do arquivo `sales_data.csv`;
- leitura com `pd.read_csv()`;
- validação das colunas obrigatórias.

### 3. Inspeção inicial da base

- visualização das primeiras linhas;
- conferência das dimensões do DataFrame;
- amostragem aleatória de registros;
- análise de tipos de dados;
- verificação de valores ausentes e duplicados;
- resumo estatístico inicial.

### 4. Tratamento e tipagem

- conversão da coluna `Date` para datetime;
- ajuste de colunas categóricas para `string`;
- ordenação dos registros por data.

### 5. Engenharia de atributos

- criação do mês da venda;
- extração do dia da semana em português;
- cálculo do lucro;
- cálculo da margem percentual;
- normalização da variável `Sales`;
- classificação da venda em faixas.

### 6. Análises descritivas

- resumo agregado por região;
- total de vendas por dia da semana;
- identificação de dias mais fortes e mais fracos;
- interpretação escrita dos padrões observados.

### 7. Visualizações

Foram produzidos diferentes tipos de gráficos para representar os dados por perspectivas complementares:

- **histograma** para distribuição dos valores de venda;
- **gráfico de dispersão** para relação entre custo e venda;
- **pairplot** para comparação entre variáveis numéricas;
- **gráfico de barras** para total de vendas por dia da semana.

### 8. Exportação da base analisada

- criação do arquivo `sales_data_analisado.csv`;
- download do CSV final a partir do Colab.

***

## Análises realizadas

### Inspeção estrutural

A base foi verificada quanto à integridade mínima para a atividade, garantindo a presença das colunas essenciais para o estudo de vendas, custo, produto, região e data.

### Resumo por região

Foi criado um agrupamento para consolidar:

- vendas totais;
- custos totais;
- lucro total;
- quantidade de transações.

Essa visão permite comparar o desempenho entre regiões e identificar onde o volume financeiro é maior.

### Vendas por dia da semana

A análise semanal foi um dos focos centrais do projeto. O agrupamento por `Day_of_Week` permitiu observar como o total de vendas varia entre os dias, respeitando uma ordem cronológica correta:

- Segunda
- Terça
- Quarta
- Quinta
- Sexta
- Sábado
- Domingo

Além disso, foram identificados:

- o maior total semanal;
- o menor total semanal;
- possíveis empates entre dias fortes e dias fracos.

### Relação entre custo, venda e lucro

Com o uso do gráfico de dispersão e do cálculo de `Profit`, foi possível examinar como os custos se relacionam com o valor vendido, além de perceber variações no retorno das transações.

***

## Principais conclusões

Com base na análise exploratória realizada, as principais conclusões do projeto foram:

- as vendas não se distribuem de maneira uniforme ao longo da semana;
- existem dias com desempenho superior e outros com menor volume de vendas;
- a observação por dia da semana ajuda a identificar padrões iniciais de comportamento comercial;
- a criação de atributos como lucro e margem amplia a capacidade de interpretação dos dados;
- visualizações complementam a leitura tabular e tornam os resultados mais fáceis de comunicar.

### Interpretação analítica

O principal padrão observado é que alguns dias concentram maior volume de vendas, enquanto outros aparecem como pontos de menor movimentação. Isso sugere influência de rotina de consumo, disponibilidade dos clientes ou dinâmica operacional do negócio.

Ao mesmo tempo, é importante manter cautela: se a amostra for pequena, os resultados devem ser tratados como **indícios iniciais**, não como regra definitiva. Para conclusões mais fortes, o ideal é repetir a análise com uma base maior e com período mais longo.

***

## Recomendações práticas

### Recomendação 1: aproveitar dias fortes

Nos dias com maior volume de vendas, vale reforçar estratégias para potencializar o resultado, como:

- aumentar atenção ao estoque;
- preparar melhor a equipe para maior movimento;
- testar promoções específicas de maior ticket médio;
- destacar produtos com maior margem.

### Recomendação 2:  desenvolver dias fracos

Nos dias com menor volume, é possível aplicar ações de estímulo comercial, por exemplo:

- criar combos promocionais;
- oferecer desconto pontual;
- divulgar campanhas de menor duração;
- testar incentivo para recompra.

A medição do resultado pode ser feita comparando o total de vendas desses dias antes e depois da ação, observando se houve crescimento consistente.

***

## Como executar no Google Colab

### Opção 1: abrir o notebook manualmente

1. Acesse o [Google Colab](https://colab.research.google.com/).
2. Faça upload do arquivo `PY-06_EDA_Vendas_Colab.ipynb`.
3. Execute as células em ordem, de cima para baixo.
4. Quando o notebook solicitar, envie o arquivo `sales_data.csv`.
5. Acompanhe as análises, gráficos e interpretações.
6. Ao final, exporte o arquivo `sales_data_analisado.csv`.

### Opção 2:  abrir a partir do GitHub

1. Publique este projeto em um repositório no GitHub.
2. No Colab, escolha a aba **GitHub**.
3. Cole a URL do repositório ou localize o notebook pelo nome.
4. Abra o arquivo `.ipynb` e execute normalmente.

***

## Boas práticas adotadas

- organização sequencial das células;
- comentários explicativos ao longo do notebook;
- validação de colunas obrigatórias;
- cuidado com ordenação temporal dos dados;
- separação entre análise tabular, visualização e interpretação;
- exportação da base enriquecida para reaproveitamento posterior.

***

## Sugestões de evolução do projeto

Como continuação da análise, o projeto pode evoluir para:

- análise por produto com ranking de desempenho;
- análise temporal por mês;
- comparação entre lucro e margem por região;
- dashboards mais interativos;
- automação da leitura do CSV sem upload manual;
- publicação de versões futuras com visualizações adicionais.

***

## Autor(a)

Tássia Nascimento  
Rio de Janeiro,RJ, Brasil  
Projeto prático de análise exploratória de dados em Python, desenvolvido no Google Colab para estudo de EDA, manipulação de dados e comunicação de resultados.
