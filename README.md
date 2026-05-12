# 📊 Superstore — Análise de Dados com Python e Looker Studio

Projeto desenvolvido por **Otávio Augusto Reis Nascimento** com foco em análise exploratória de dados (EDA), tratamento de dados, geração de KPIs e visualização interativa utilizando Python, Google Colab e Google Looker Studio.

---

# 📌 Objetivo do Projeto

Realizar a análise de dados da base **Sample Superstore**, identificando padrões de vendas, lucratividade, impacto de descontos, comportamento de clientes e oportunidades estratégicas para tomada de decisão.

---

# 🛠️ Tecnologias Utilizadas

* Python
* Google Colab
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Plotly
* Google Looker Studio

---

# 📂 Estrutura do Projeto

```bash
📁 superstore-analise
│
├── analise_de_vendas_Superstore.ipynb
├── dados_tratados.csv
├── README.md
└── Sample - Superstore.csv
```

---

# 🚀 Etapas de Desenvolvimento

## 1. Configuração do Ambiente

Utilização do:

* Google Colab
* Google Looker Studio

Instalação e importação das bibliotecas:

```python
!pip install plotly --quiet
```

Bibliotecas utilizadas:

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
import plotly.express as px
```

---

## 2. Configurações Visuais

Padronização do estilo gráfico utilizando:

* `seaborn.set_theme()`
* `plt.rcParams`

Objetivos:

* Melhorar a legibilidade
* Padronizar visualizações
* Tornar dashboards mais profissionais

---

## 3. Carregamento dos Dados

Upload do arquivo:

```bash
Sample - Superstore.csv
```

Leitura dos dados em um DataFrame Pandas.

---

## 4. Exploração Inicial dos Dados

Foram realizadas análises preliminares utilizando:

```python
df.head()
df.info()
df.describe()
```

Também foram verificadas:

* Quantidade de valores nulos
* Dados duplicados
* Tipos de dados
* Estatísticas gerais

---

# 🧹 Tratamento e Preparação dos Dados

## Remoção de Duplicatas

```python
df.drop_duplicates()
```

Mesmo sem duplicatas identificadas inicialmente, a etapa foi mantida para garantir robustez futura.

---

## Padronização das Colunas

Conversão para padrão `snake_case`.

### Antes

```bash
Order Date
Ship-Date
```

### Depois

```bash
order_date
ship_date
```

Benefícios:

* Melhor legibilidade
* Menor chance de erros
* Código mais organizado

---

## Conversão de Tipos

### Datas

Conversão das colunas:

* `order_date`
* `ship_date`

Para o tipo:

```python
datetime
```

Utilizando:

```python
errors='coerce'
dayfirst=True
```

---

### Colunas Numéricas

Conversão das colunas:

* `sales`
* `profit`
* `discount`
* `quantity`

Para tipos numéricos:

```python
float64
int64
```

---

## Tratamento de Valores Nulos

### Colunas Numéricas

Preenchimento com a mediana.

### Colunas Categóricas

Preenchimento com:

```python
'Desconhecido'
```

---

# 📊 Tratamento de Outliers

Identificação de outliers utilizando o método:

## IQR (Interquartile Range)

Colunas analisadas:

* `sales`
* `profit`
* `discount`

Visualizações realizadas com:

* Boxplots
* Distribuições estatísticas

Os outliers não foram removidos, apenas identificados para análise estratégica.

---

# 📈 Análise Exploratória dos Dados (EDA)

## 📌 Vendas e Lucro por Categoria

Análise das categorias:

* Tecnologia
* Mobiliário
* Material de Escritório

Visualizações:

* Gráficos de barras
* Comparativos de vendas e lucro

---

## 👥 Segmentação de Clientes

Segmentos analisados:

* Consumidor
* Corporativo
* Home Office

Indicadores:

* Total de vendas
* Lucro total
* Margem média

Visualizações:

* Gráficos de pizza
* Comparativos percentuais

---

## 💸 Impacto dos Descontos

Criação de faixas de desconto:

* Sem desconto
* 1% a 10%
* 11% a 20%
* Acima de 20%

Análises realizadas:

* Relação entre desconto e lucro
* Lucro médio por faixa
* Impacto financeiro dos descontos

Visualizações:

* Gráfico de dispersão
* Gráfico de barras

---

## 📅 Tendências Temporais

Extração de:

* Ano
* Mês

Análise da evolução:

* Vendas
* Lucro

Visualizações:

* Gráficos de linha interativos

---

## 🔥 Correlação entre Variáveis

Geração de:

* Heatmap de correlação

Análises entre:

* Sales
* Profit
* Discount
* Quantity

---

# 📌 KPIs Principais

| Indicador        | Valor           |
| ---------------- | --------------- |
| Total de Vendas  | R$ 2.297.200,86 |
| Total de Lucro   | R$ 286.397,02   |
| Margem de Lucro  | 12,47%          |
| Ticket Médio     | R$ 229,86       |
| Total de Pedidos | 9.994           |
| Desconto Médio   | 15,62%          |

---

# 📊 Insights Principais

## Tecnologia

* Principal categoria em vendas e lucro
* Melhor desempenho geral

---

## Mobiliário

* Alto volume de vendas
* Baixa lucratividade
* Necessidade de revisão estratégica

---

## Material de Escritório

* Excelente eficiência operacional
* Melhor relação entre vendas e lucro

---

# 👤 Análise por Segmento

## Consumidor

* Maior volume de vendas
* Menor margem média

## Corporativo

* Boa rentabilidade
* Margem superior ao consumidor

## Home Office

* Maior margem média
* Melhor rentabilidade por transação
* Potencial de expansão

---

# 💰 Impacto dos Descontos

## Cenários Identificados

### Descontos de 1% a 10%

✅ Maior lucratividade

### Descontos de 11% a 20%

⚠️ Lucro reduzido

### Descontos acima de 20%

❌ Prejuízo médio negativo

---

# 📈 Tendências Temporais

Foi identificado:

* Crescimento geral de vendas
* Crescimento do lucro ao longo dos anos
* Forte sazonalidade em determinados períodos

---

# 🔗 Correlações Importantes

| Variáveis         | Correlação |
| ----------------- | ---------- |
| Sales × Profit    | 0.48       |
| Discount × Profit | -0.22      |
| Quantity × Sales  | 0.20       |
| Quantity × Profit | 0.07       |

---

# 🎯 Recomendações Estratégicas

## 1. Reavaliar Política de Descontos

Evitar descontos acima de:

```bash
20%
```

---

## 2. Otimizar Categoria Mobiliário

Revisar:

* Custos
* Precificação
* Estratégias comerciais

---

## 3. Expandir Segmento Home Office

Investir em:

* Campanhas específicas
* Produtos direcionados
* Estratégias de crescimento

---

## 4. Investigar Outliers

Analisar transações atípicas para:

* Identificar oportunidades
* Detectar problemas operacionais

---

## 5. Planejamento Sazonal

Utilizar tendências temporais para:

* Estoque
* Promoções
* Marketing

---

# ▶️ Guia de Execução

## 1. Ambiente

Utilize:

* Google Colab
* Jupyter Notebook

---

## 2. Upload do Dataset

Faça upload do arquivo:

```bash
Sample - Superstore.csv
```

---

## 3. Execute o Notebook

Execute todas as células em ordem:

```bash
Runtime → Run All
```

---

## 4. Resultado

Ao final será gerado:

```bash
dados_tratados.csv
```

Com todos os dados tratados e preparados.

---

# 📊 Dashboard no Looker Studio

O arquivo tratado foi utilizado no Google Looker Studio para criação de dashboards interativos com:

* KPIs principais
* Filtros por período
* Filtros por categoria
* Filtros por segmento
* Análises temporais

## 🔗 Acesse o Dashboard

[https://datastudio.google.com/reporting/469d1b38-075a-46d6-bd00-22ba2993314e](https://datastudio.google.com/reporting/469d1b38-075a-46d6-bd00-22ba2993314e)

---

# ✅ Resultado Final

Projeto completo de análise de dados com:

* Tratamento de dados
* Análise exploratória
* Visualização gráfica
* KPIs estratégicos
* Dashboard interativo

Focado em transformar dados brutos em informações úteis para tomada de decisão.

