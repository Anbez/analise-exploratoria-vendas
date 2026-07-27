# Análise Exploratória de Dados de Vendas (EDA)

Projeto prático desenvolvido na aula **PY-06 — Análise Exploratória de Dados (EDA)** do Bootcamp de Análise de Dados. O objetivo principal é inspecionar, tratar, analisar e extrair *insights* práticos a partir de uma base de dados de vendas, utilizando a linguagem Python no ambiente Google Colab.

---

## 🎯 Objetivo do Projeto

- Carregar e inspecionar a qualidade, integridade e estrutura dos dados de vendas.
- Realizar engenharia de atributos (criação de colunas temporais, lucro, margem de lucro e classificação de vendas).
- Produzir análises não visuais (agrupamentos e agregações) e visuais (distribuições e relações entre variáveis).
- Identificar padrões de desempenho por dia da semana e região.
- Propor recomendações estratégicas de negócio baseadas nos achados da análise.

---

## 📂 Origem e Nome do Conjunto de Dados

- **Nome da base:** `sales_data.csv`
- **Descrição:** Conjunto de dados contendo registros de transações de vendas com as seguintes variáveis originais:
  - `Sales`: valor bruto da venda (R$).
  - `Cost`: custo associado à venda (R$).
  - `Region`: região onde a venda foi realizada (`North`, `South`, `East`, `West`).
  - `Product`: categoria/código do produto (`A`, `B`, `C`, `D`).
  - `Date`: data da transação.

---

## 🛠️ Bibliotecas Utilizadas

- **[Pandas](https://pandas.pydata.org/):** manipulação, limpeza, agrupamento e engenharia de atributos dos dados.
- **[NumPy](https://numpy.org/):** suporte a operações matemáticas, lógicas e condicionais vetorizadas.
- **[Matplotlib](https://matplotlib.org/):** construção da estrutura de gráficos e customizações de eixos/títulos.
- **[Seaborn](https://seaborn.pydata.org/):** visualizações estatísticas atrativas (histogramas, scatter plots, pairplots).

---

## 🔄 Etapas da Análise

1. **Preparação e Conexão:** Configuração do ambiente no Google Colab e carregamento do arquivo `sales_data.csv`.
2. **Inspeção Inicial:** Verificação de dimensões, nomes de colunas, tipos de dados, ausência de nulos e contagem de duplicatas.
3. **Tratamento de Dados:** Conversão da coluna `Date` para o tipo `datetime` e ordenação cronológica dos registros.
4. **Engenharia de Atributos:** Criação das colunas:
   - `Month` e `Day_of_Week` (dia da semana em português).
   - `Profit` (Lucro = Vendas − Custo) e `Margin_Percent` (Margem de Lucro %).
   - `Sales_Normalized` (escala de 0 a 1) e `Sales_Tier` (Classificação: *Alta* > 300 / *Baixa* <= 300).
5. **Análise Não Visual:** Agrupamentos por região e por dia da semana para identificar picos e vales de receita.
6. **Análise Visual:** Elaboração de histogramas, gráfico de dispersão (Custo x Venda x Lucro), pairplot e gráfico de barras semanal.
7. **Relatório de Conclusões & Recomendações:** Síntese dos achados e propostas práticas para tomada de decisão.
8. **Exportação:** Geração e download do arquivo enriquecido `sales_data_analisado.csv`.

---

## 💡 Principais Conclusões

- **Padrão Semanal de Vendas:**
  - O maior volume de vendas concentra-se na **Terça-feira** (R$ 1.000) e na **Segunda-feira** (R$ 700), indicando forte início de semana.
  - O menor volume ocorre na **Quarta-feira** e no **Domingo** (R$ 200 cada).
- **Desempenho Regional:**
  - A região **North** lidera o volume de faturamento e lucro total, seguida pela região **East**.
  - A região **West** apresentou o menor faturamento total e a menor margem de lucro acumulada.
- **Relação Custo x Venda:**
  - Existe uma forte correlação positiva entre o custo dos produtos e o valor total de venda, mantendo margens de lucro relativamente estáveis.
- **Cuidado com a Interpretação:**
  - Como a amostragem da atividade é reduzida (10 transações), os padrões observados representam comportamentos pontuais e exigem cautela antes de serem generalizados para decisões de longo prazo sem uma base histórica maior.

### 📋 Recomendações Práticas
1. **Aproveitar Dias Fortes:** Alocar maior orçamento de mídia paga e campanhas de anúncios digitais entre domingo à noite e terça-feira, garantindo estoque preparado para atender o pico de faturamento do início da semana.
2. **Desenvolver Dias Fracos:** Criar ofertas exclusivas para o meio da semana (ex: "Quarta Off" ou cupom de frete grátis) para estimular a conversão nos dias de menor engajamento, acompanhando a evolução da taxa de conversão e ticket médio nesses dias específicos.

---

## 🚀 Instruções para Executar no Google Colab

1. Faça o download do repositório ou baixe os arquivos `PY-06_EDA_Vendas_Colab.ipynb` e `sales_data.csv`.
2. Acesse o [Google Colab](https://colab.research.google.com/).
3. Clique em **Arquivo → Fazer upload do notebook** e selecione o arquivo `.ipynb`.
4. Execute a célula da **Seção 2** e clique no botão **Escolher arquivos** para enviar o arquivo `sales_data.csv`.
5. Execute as demais células sequencialmente usando `Shift + Enter` ou no menu **Ambiente de execução → Executar tudo**.
6. Ao final, a célula de exportação fará o download automático da base tratada (`sales_data_analisado.csv`).
