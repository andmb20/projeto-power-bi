# 📊 Análise de Vendas — Power BI

## 🎯 Objetivo

Projeto de análise de dados desenvolvido com Power BI, com o objetivo de transformar dados de vendas em informações e indicadores que auxiliem na análise do desempenho comercial.

O projeto contempla desde a preparação e modelagem dos dados até a construção de um dashboard interativo e geração de insights.

## 🗂️ Dados

O projeto utiliza uma base de dados fictícia composta por quatro arquivos Excel:

| Arquivo          | Descrição               | Registros |
| ---------------- | ----------------------- | --------: |
| `Vendas.xlsx`    | Registros de vendas     |     8.391 |
| `Produtos.xlsx`  | Cadastro de produtos    |     1.210 |
| `Lojas.xlsx`     | Cadastro de lojas       |       786 |
| `Devolucao.xlsx` | Registros de devoluções |       548 |

Os dados são fictícios e utilizados exclusivamente para fins de estudo e desenvolvimento de portfólio.

## 🧩 Modelagem dos Dados

O modelo de dados está sendo construído no Power BI utilizando relacionamentos entre as tabelas.

Relacionamentos identificados até o momento:

* `Produtos[Produto_sku]` → `Vendas[Produto_sku]`
* `Lojas[Loja_id]` → `Vendas[Loja_id]`
* `Vendas[venda_id]` → `Devolução[Venda_id]`

A documentação da modelagem será complementada conforme o desenvolvimento do projeto.

## 🛠️ Tecnologias

* Power BI
* DAX
* Microsoft Excel
* Git
* GitHub

## 📈 Dashboard

> Em desenvolvimento.

## 🔎 Insights

> Serão adicionados após a conclusão das análises.

## 📁 Estrutura do Projeto

```text
projeto-power-bi/
│
├── dados/
│   ├── vendas.xlsx
│   ├── produtos.xlsx
│   ├── lojas.xlsx
│   └── devolucao.xlsx
│
├── documentacao/
│
├── imagens/
│
├── powerbi/
│   └── projeto-vendas.pbix
│
└── README.md
```

## 🚧 Status

**Em desenvolvimento.**
