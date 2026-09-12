# Medidas DAX

## 1. Objetivo

Documentar as principais medidas DAX utilizadas no projeto, seus objetivos e as validações realizadas no Power BI.

As medidas foram criadas para suportar os principais indicadores definidos na etapa de requisitos do projeto e permitir análises de faturamento, vendas, custos, lucro, devoluções e desempenho ao longo do tempo.

---

## 2. Medidas principais

### Faturamento

```DAX
Faturamento =
SUM(Vendas[Venda_Total])
```

Representa o valor total das vendas realizadas.

---

### Quantidade de Vendas

```DAX
Quantidade de Vendas =
DISTINCTCOUNT('Vendas'[Venda_id])
```

Representa a quantidade de vendas realizadas, considerando cada `Venda_id` uma única vez.

---

### Quantidade de Produtos Vendidos

```DAX
Quantidade de Produtos Vendidos =
SUM('Vendas'[Venda_QTD])
```

Representa a quantidade total de produtos vendidos.

---

### Custo

```DAX
Custo =
SUM('Vendas'[Venda_Custo])
```

Representa o custo total associado às vendas.

---

### Lucro

```DAX
Lucro Calc =
SUM('Vendas'[Lucro])
```

Representa o lucro total das vendas.

A medida foi criada a partir da coluna `Lucro` existente na tabela `Vendas`, permitindo sua utilização em outros cálculos DAX.

---

### Devoluções

```DAX
Devoluções =
DISTINCTCOUNT('Devolução'[Venda_id])
```

Representa a quantidade de vendas que possuem registro de devolução.

---

### % Devolução

```DAX
% Devolução =
DIVIDE(
    [Devoluções],
    [Quantidade de Vendas]
)
```

Representa a proporção de vendas que possuem devolução em relação ao total de vendas.

---

## 3. Indicadores derivados

### Ticket Médio

```DAX
Ticket Médio =
DIVIDE(
    [Faturamento],
    [Quantidade de Vendas]
)
```

Representa o faturamento médio por venda.

---

### Margem %

```DAX
Margem % =
DIVIDE(
    [Lucro Calc],
    [Faturamento]
)
```

Representa a proporção do faturamento que corresponde ao lucro.

---

### Crescimento %

```DAX
Crescimento % =
VAR FaturamentoAtual = [Faturamento]
VAR FaturamentoAnterior =
    CALCULATE(
        [Faturamento],
        DATEADD('Calendário'[Date], -1, MONTH)
    )
RETURN
    DIVIDE(
        FaturamentoAtual - FaturamentoAnterior,
        FaturamentoAnterior
    )
```

Representa a variação percentual do faturamento em relação ao mês anterior.

O cálculo utiliza a tabela `Calendário` para realizar a comparação temporal.

---

## 4. Validação das medidas

As medidas foram testadas individualmente no Power BI por meio de cartões e visualizações.

Principais resultados observados:

| Indicador                       |               Resultado |
| ------------------------------- | ----------------------: |
| Quantidade de Vendas            |                   8.391 |
| Quantidade de Produtos Vendidos | aproximadamente 215 mil |
| Devoluções                      |                     528 |
| % Devolução                     |                   6,29% |
| Ticket Médio                    |               R$ 844,26 |
| Margem %                        |                  53,96% |

Os valores obtidos foram considerados coerentes com os dados disponíveis e com as validações realizadas anteriormente no Power Query.

---

## 5. Validação temporal

A medida `Crescimento %` foi validada por meio de um gráfico de linhas utilizando:

* **Eixo X:** `Calendário[Ano-Mês]`
* **Eixo Y:** `[Faturamento]`
* **Eixo secundário:** `[Crescimento %]`

O período analisado compreende janeiro de 2018 a dezembro de 2021.

O eixo temporal foi configurado em ordem cronológica crescente para evitar interpretações incorretas causadas por ordenação alfabética.

Foi observado que o faturamento apresenta oscilações mensais relevantes, com períodos de crescimento e retração.

Também foram observados picos de crescimento em maio de 2019 e maio de 2021, seguidos por retrações nos meses posteriores.

Esses comportamentos representam padrões observados no período analisado e não estabelecem relação causal.

---

## 6. Decisões e observações

### Lucro

A tabela `Vendas` já possui a coluna `Lucro`. Foi criada a medida `Lucro Calc` para permitir sua utilização nos cálculos agregados e na medida de `Margem %`.

### Faturamento líquido após devoluções

Não foi criada uma medida de faturamento líquido após devoluções.

A tabela `Devolução` possui informações sobre os registros de devolução, mas não possui um valor monetário associado à devolução. Portanto, não é possível calcular de forma confiável o valor financeiro devolvido apenas com os dados disponíveis.

### Crescimento

O crescimento foi calculado em relação ao mês anterior utilizando a tabela `Calendário`.

A análise de crescimento deve ser interpretada em conjunto com o faturamento, principalmente em visualizações temporais.

---

## 7. Conclusão

As principais medidas necessárias para os indicadores definidos na etapa de requisitos foram implementadas e validadas no Power BI.

As medidas permitem analisar:

* Faturamento;
* Quantidade de vendas;
* Quantidade de produtos vendidos;
* Custos;
* Lucro;
* Margem;
* Devoluções;
* Percentual de devoluções;
* Ticket médio;
* Crescimento mensal do faturamento.

Com a conclusão desta etapa, os indicadores fundamentais do modelo estão preparados para serem utilizados nas próximas etapas de construção e análise do dashboard.
