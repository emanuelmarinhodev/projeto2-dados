# 📊 Análise de Vendas e Performance de Pedidos

Este projeto consiste em uma análise exploratória e tratamento de dados de um sistema de pedidos. O objetivo principal foi realizar o processo de ETL (Extração, Transformação e Carga), integrando informações de vendas com o cardápio de produtos para gerar indicadores de desempenho (KPIs) e insights estratégicos para o negócio.

## 🛠️ Tecnologias Utilizadas

* **Python 3.x**
* **Pandas**: Manipulação, limpeza e agregação de dados.
* **NumPy**: Processamento matemático e cálculos de estatística descritiva (percentis).
* **Jupyter Notebook**: Ambiente para desenvolvimento e documentação da análise.

## 📁 Estrutura dos Dados

O projeto consome dois datasets localizados na pasta `dataset/`:
* `pedidos.csv`: Histórico de transações contendo ID, Data, Cliente, Item, Quantidade e Preços.
* `cardapio.csv`: Tabela de referência com a categorização dos produtos e preços base.

## ⚙️ Etapas do Processo

### 1. Limpeza e Tratamento (Data Cleaning)
* **Tratamento de Nulos:** Preenchimento de quantidades ausentes através da média e remoção de registros inconsistentes sem preço unitário.
* **Conversão de Tipos:** Ajuste da coluna `Quantidade` para inteiro (int) e `Data` para o formato datetime.
* **Feature Engineering:** Cálculo de receita por item e extração de colunas temporais (Mês) para análises de sazonalidade.

### 2. Integração e Enriquecimento (Merge)
* Cruzamento de dados entre pedidos e cardápio utilizando `left join` para atribuir **Categorias** aos itens vendidos, permitindo uma visão macro do faturamento.

### 3. Análise Exploratória e Agregações
* Identificação dos itens campeões de vendas e de faturamento.
* Agrupamentos por categoria para identificar o carro-chefe da operação.

## 📈 Principais Indicadores (KPIs)

| Indicador | Valor Calculado |
| :--- | :--- |
| **Receita Total Gerada** | R$ 122.652,59 |
| **Ticket Médio por Pedido** | R$ 285,24 |
| **Quantidade Total Vendida** | 6.817 itens |
| **Categoria Líder** | Salgados |

## 📊 Análise Estatística (Distribuição)

Utilizando funções de percentis do **NumPy**, identificamos o comportamento dos dados:
* **Preço Unitário:** A mediana (50%) dos produtos está em **R$ 13,09**, indicando um mix de produtos acessíveis.
* **Volume por Pedido:** 75% dos pedidos (Q3) contêm até **24 unidades** de um mesmo item.

