# Contexto e Requisitos de Negócio

## 1. Objetivo do projeto

Desenvolver um dashboard no Power BI para fornecer ao Head de Vendas uma visão detalhada do desempenho comercial da empresa, permitindo analisar as vendas por período, produto, categoria, canal e localização.

O dashboard deverá complementar a visão de alto nível já existente, permitindo identificar quais produtos e tipos de roupas apresentam maior volume de vendas e como o comportamento das vendas varia entre os estados.

---

## 2. Usuário do dashboard

**Usuário principal:** Head de Vendas

O dashboard deverá apoiar o acompanhamento do desempenho comercial e a identificação de oportunidades de vendas por produto, categoria, canal e localização.

---

## 3. Perguntas de negócio

O dashboard deverá permitir responder, entre outras, às seguintes perguntas:

### Desempenho geral

* Qual é o valor total das vendas?
* Qual é o volume de vendas?
* Qual é o lucro obtido?
* Qual é a margem de lucro?
* Como as vendas evoluem ao longo do tempo?
* Qual é o impacto das devoluções sobre as vendas?

### Produtos

* Quais produtos apresentam maior volume de vendas?
* Quais produtos geram maior faturamento?
* Quais produtos geram maior lucro?
* Quais categorias/tipos de roupas apresentam melhor desempenho?

### Lojas e canais

* Quais canais apresentam maior volume de vendas?
* Quais lojas apresentam melhor desempenho?
* Como o desempenho varia entre os diferentes canais?

### Localização

* Quais estados apresentam maior volume de vendas?
* Quais estados apresentam maior faturamento?
* Quais produtos ou categorias são mais vendidos em cada estado?
* Existem diferenças relevantes no comportamento de vendas entre os estados?

---

## 4. Indicadores (KPIs)

Os principais indicadores a serem considerados são:

* Faturamento / valor total das vendas
* Quantidade de vendas
* Quantidade de produtos vendidos, quando disponível
* Custo dos produtos
* Lucro
* Margem de lucro
* Valor ou quantidade de devoluções
* Faturamento líquido após devoluções, caso os dados permitam esse cálculo

Os indicadores deverão poder ser analisados por diferentes dimensões do negócio.

---

## 5. Dimensões de análise

### Tempo

* Data
* Ano
* Mês

### Produto

* Produto
* SKU
* Categoria/tipo de roupa

### Loja

* Loja
* Canal
* Cidade
* Região
* Estado
* País

### Devolução

* Data da devolução
* Ano
* Mês
* Dia
* Hora

---

## 6. Fontes de dados

O projeto utiliza quatro arquivos Excel:

* `Vendas.xlsx`
* `Produtos.xlsx`
* `Lojas.xlsx`
* `Devolucao.xlsx`

As tabelas foram importadas para o Power BI e avaliadas no Power Query.

---

## 7. Modelo de dados identificado

As tabelas apresentam os seguintes relacionamentos principais:

```text
Produtos[Produto_sku]  1 ───── * Vendas[Produto_sku]

Lojas[Loja_id]         1 ───── * Vendas[Loja_id]

Vendas[Venda_id]       1 ───── * Devolução[Venda_id]
```

A tabela `Vendas` funciona como a principal tabela transacional do modelo.

`Produtos` fornece informações relacionadas aos produtos.

`Lojas` fornece informações relacionadas às lojas, canais e localização.

`Devolução` registra ocorrências relacionadas às vendas realizadas.

---

## 8. Critérios iniciais de análise

O dashboard deverá priorizar:

1. Visão geral do desempenho comercial;
2. Evolução das vendas ao longo do tempo;
3. Desempenho por produto e categoria;
4. Desempenho por canal;
5. Desempenho por estado;
6. Relação entre produtos/categorias e estados;
7. Impacto das devoluções.

As decisões finais de visualização e os KPIs definitivos serão definidos durante as etapas de modelagem e desenvolvimento do dashboard.
