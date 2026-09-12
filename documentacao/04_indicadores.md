# Indicadores de Desempenho

## 1. Objetivo

Definir os principais indicadores de desempenho que serão utilizados no dashboard do Power BI.

Os indicadores foram definidos a partir dos requisitos de negócio levantados para a análise detalhada das vendas, produtos, lojas e devoluções.

---

## 2. KPIs principais

### 2.1 Faturamento

**Objetivo:**

Mensurar o valor total das vendas realizadas no período analisado.

**Fórmula/conceito:**

Soma do valor total das vendas.

**Campo utilizado:**

`Vendas[Venda_Total]`

---

### 2.2 Quantidade de vendas

**Objetivo:**

Mensurar a quantidade de vendas realizadas.

**Fórmula/conceito:**

Contagem distinta dos identificadores de venda.

**Campo utilizado:**

`Vendas[Venda_id]`

**Observação:**

Foi definida a utilização de contagem distinta para evitar que uma mesma venda seja contabilizada mais de uma vez.

---

### 2.3 Lucro

**Objetivo:**

Mensurar o resultado financeiro obtido nas vendas.

**Fórmula/conceito:**

Soma do lucro registrado para as vendas.

**Campo utilizado:**

`Vendas[Lucro]`

---

### 2.4 Margem

**Objetivo:**

Mensurar a representatividade do lucro em relação ao faturamento.

**Fórmula/conceito:**

`Lucro ÷ Faturamento`

**Campos utilizados:**

* `Vendas[Lucro]`
* `Vendas[Venda_Total]`

**Observação:**

O resultado será apresentado em formato percentual.

---

### 2.5 Devoluções

**Objetivo:**

Mensurar a quantidade de vendas que possuem registro de devolução.

**Fórmula/conceito:**

Contagem distinta dos identificadores de venda presentes na tabela de devoluções.

**Campo utilizado:**

`Devolução[Venda_id]`

**Observação:**

Uma mesma venda pode possuir mais de um registro na tabela `Devolução`. Por isso, será utilizada contagem distinta.

---

### 2.6 % de devolução

**Objetivo:**

Mensurar a proporção de vendas que possuem registro de devolução em relação ao total de vendas.

**Fórmula/conceito:**

`Quantidade de vendas devolvidas ÷ Quantidade total de vendas`

**Campos utilizados:**

* `Devolução[Venda_id]`
* `Vendas[Venda_id]`

**Observação:**

O resultado será apresentado em formato percentual.

---

## 3. Indicadores derivados

### 3.1 Ticket médio

**Objetivo:**

Mensurar o valor médio de cada venda.

**Fórmula/conceito:**

`Faturamento ÷ Quantidade de vendas`

**Campos utilizados:**

* `Vendas[Venda_Total]`
* `Vendas[Venda_id]`

---

### 3.2 Faturamento por período

**Objetivo:**

Analisar a evolução do faturamento ao longo do tempo.

**Fórmula/conceito:**

Faturamento agrupado por período.

**Campos utilizados:**

* `Vendas[Venda_Total]`
* `Vendas[Venda_Data]`

---

### 3.3 Crescimento percentual

**Objetivo:**

Comparar o faturamento de diferentes períodos e identificar crescimento ou redução das vendas.

**Fórmula/conceito:**

`(Faturamento do período atual − Faturamento do período anterior) ÷ Faturamento do período anterior`

**Campos utilizados:**

* `Vendas[Venda_Total]`
* `Vendas[Venda_Data]`

**Observação:**

Esse indicador será implementado posteriormente com DAX e dependerá da estrutura temporal utilizada no modelo.

---

## 4. Indicadores não implementados neste momento

### Faturamento líquido após devoluções

**Motivo:**

A tabela `Devolução` possui o identificador da venda e informações de data/hora, mas não possui um campo com o valor monetário devolvido.

Portanto, não é possível calcular de forma confiável:

`Faturamento − Valor devolvido`

sem realizar uma suposição sobre o valor financeiro de cada devolução.

Por esse motivo, o indicador não será criado nesta etapa.

---

## 5. Resumo dos indicadores

| Indicador               | Prioridade | Situação         |
| ----------------------- | ---------: | ---------------- |
| Faturamento             |       Alta | Definido         |
| Quantidade de vendas    |       Alta | Definido         |
| Lucro                   |       Alta | Definido         |
| Margem                  |       Alta | Definido         |
| Devoluções              |       Alta | Definido         |
| % de devolução          |       Alta | Definido         |
| Ticket médio            |      Média | Definido         |
| Faturamento por período |      Média | Definido         |
| Crescimento %           |      Média | Definido         |
| Faturamento líquido     |          — | Não implementado |

---

## 6. Próxima etapa

Após a definição dos indicadores, serão criadas as respectivas medidas DAX no Power BI.

As medidas serão validadas individualmente antes da construção dos visuais do dashboard.
