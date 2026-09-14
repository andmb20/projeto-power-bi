# Análise exploratória

## 1. Objetivo

A análise exploratória foi realizada no Power BI com o objetivo de identificar padrões de vendas, faturamento, comportamento por localização, desempenho dos canais e devoluções.

As análises foram realizadas a partir das tabelas `Vendas`, `Produtos`, `Lojas`, `Devolução` e `Calendário`, utilizando as medidas DAX definidas na etapa anterior.

O objetivo desta etapa é transformar os indicadores calculados em informações relevantes para a tomada de decisão e responder às principais perguntas definidas nos requisitos do projeto.

---

## 2. Análise temporal

### Vendas ao longo do tempo

A análise temporal considera a evolução das vendas ao longo do período disponível na base, compreendido entre janeiro de 2018 e dezembro de 2021.

**Visualização utilizada:**

* **Eixo X:** `Calendário[Ano-Mês]`
* **Eixo Y:** `[Quantidade de Vendas]`
* **Ordenação:** cronológica crescente

A análise permite identificar períodos de maior e menor volume de vendas e observar a evolução do comportamento comercial ao longo do tempo.

O faturamento apresentou oscilações mensais relevantes durante o período analisado, com períodos de crescimento e retração.

O maior faturamento mensal foi observado em **maio de 2021**, enquanto o menor faturamento ocorreu em **dezembro de 2021**.

Foi realizada uma validação adicional para confirmar que dezembro de 2021 possuía todos os dias do mês representados na tabela `Vendas`, evitando que o resultado fosse influenciado por um período incompleto.

Também foram observados picos de crescimento do faturamento em **maio de 2019** e **maio de 2021**, seguidos por retrações nos meses posteriores.

Esses comportamentos representam padrões observados no período analisado e não estabelecem relação causal.

---

## 3. Produtos

### Categorias mais vendidas

A análise das categorias foi realizada utilizando a medida **Quantidade de Produtos Vendidos**, que representa o total de unidades comercializadas.

O ranking geral de unidades vendidas foi:

| Categoria     | Unidades vendidas |
| ------------- | ----------------: |
| Moletom       |            59.102 |
| Camisetas     |            35.244 |
| Jaquetas      |            34.156 |
| Calças        |            30.626 |
| Shorts        |            24.936 |
| Regatas       |            17.942 |
| Sutiãs e Tops |            11.706 |
| Em branco     |               883 |

A categoria **Moletom** apresentou o maior volume de unidades vendidas, com **59.102 unidades**, seguida por **Camisetas**, com 35.244 unidades, e **Jaquetas**, com 34.156 unidades.

Na análise por estado, o Moletom foi a categoria com maior quantidade de unidades vendidas em **15 dos 17 estados analisados**.

Com exceções nos estados do **Acre (AC)**, onde **Calças** apresentaram o maior volume, com **146 unidades vendidas**, contra **143 unidades de Moletom** e **Amapá (AP)** onde **Camisetas** apresentaram o maior volume, com **532 unidades vendidas**, contra **416 unidades de Moletom**

Esse resultado demonstra uma forte predominância do Moletom no comportamento de vendas da base, tanto no volume geral quanto na maioria dos estados.

---

### Faturamento por categoria

A análise do faturamento por categoria permite identificar quais categorias apresentam maior contribuição financeira para o resultado.

| Categoria     |  Faturamento |
| ------------- | -----------: |
| Moletom       | R$ 1.931.691 |
| Jaquetas      | R$ 1.806.935 |
| Calças        | R$ 1.309.042 |
| Shorts        |   R$ 874.297 |
| Camisetas     |   R$ 536.139 |
| Regatas       |   R$ 362.156 |
| Sutiãs e Tops |   R$ 236.097 |
| Em branco     |    R$ 27.797 |

A categoria **Moletom** apresentou o maior faturamento, com **R$ 1.931.691**, seguida por **Jaquetas**, com R$ 1.806.935.

A categoria Moletom apresentou, portanto, tanto o maior volume de unidades vendidas quanto o maior faturamento entre as categorias.

---

### Produtos com maior faturamento

A análise dos produtos foi realizada considerando o faturamento gerado por cada produto, com ordenação decrescente.

| Posição | Produto                                 | Faturamento |
| ------: | --------------------------------------- | ----------: |
|       1 | Hyperion EleMasculinots Jaqueta         |  R$ 207.449 |
|       2 | Orion Two-Tone Fitted Jaqueta           |  R$ 197.596 |
|       3 | Beaumont Summit Kit                     |  R$ 173.688 |
|       4 | Kenobi Trail Jaqueta                    |  R$ 159.453 |
|       5 | Proteus Fitness Jackshirt               |  R$ 157.926 |
|       6 | Typhon Performance Fleece-lined Jaqueta |  R$ 156.404 |
|       7 | Montana Wind Jaqueta                    |  R$ 155.365 |
|       8 | Lando Gym Jaqueta                       |  R$ 154.722 |
|       9 | Mars HeatTech Pullover                  |  R$ 150.547 |
|      10 | Taurus EleMasculinots Shell             |  R$ 147.090 |

O produto **Hyperion EleMasculinots Jaqueta** apresentou o maior faturamento individual, com aproximadamente **R$ 207,4 mil**.

Observa-se também uma forte presença de produtos da categoria **Jaquetas** entre os produtos com maior faturamento individual.

---

### Devoluções por produto

A análise foi realizada considerando a quantidade de registros de devolução associados a cada produto.

Os produtos com maior quantidade de registros de devolução foram:

| Produto                                 | Devoluções |
| --------------------------------------- | ---------: |
| Hero Moletom                            |         14 |
| Stark FundaMasculinotal Moletom         |         13 |
| Deion Manga longa EverCool Camiseta     |         12 |
| Mithra Warmup Calça                     |         12 |
| Zoltan Gym Camiseta                     |         12 |
| Hyperion EleMasculinots Jaqueta         |         11 |
| Montana Wind Jaqueta                    |         11 |
| Chaz Kangeroo Moletom                   |         10 |
| Cinzason Crewneck Sweatshirt            |         10 |
| Electra Sutiã Top                       |         10 |
| Jupiter All-Weather Trainer             |         10 |
| Kratos Gym Calça                        |         10 |
| Orestes Yoga Calça                      |         10 |
| Primo Endurance Regata                  |         10 |
| Ryker LumaTech Camiseta (Gola V)        |         10 |
| Typhon Performance Fleece-lined Jaqueta |         10 |

O produto **Hero Moletom** apresentou a maior quantidade de registros de devolução, com **14 ocorrências**.

---

## 4. Localização

### Faturamento por estado

A análise do faturamento por estado permite comparar a contribuição de cada unidade federativa para o resultado geral.

| Estado |  Faturamento |
| ------ | -----------: |
| RO     | R$ 1.882.704 |
| MA     | R$ 1.306.470 |
| PR     |   R$ 846.069 |
| MG     |   R$ 721.560 |
| SC     |   R$ 499.024 |
| RR     |   R$ 481.313 |
| PA     |   R$ 480.046 |
| ES     |   R$ 157.600 |
| RJ     |   R$ 145.978 |
| CE     |   R$ 110.839 |
| BA     |   R$ 109.364 |
| RS     |    R$ 94.820 |
| PI     |    R$ 89.612 |
| AP     |    R$ 74.337 |
| TO     |    R$ 36.131 |
| AM     |    R$ 28.069 |
| AC     |    R$ 20.218 |

**Rondônia (RO)** apresentou o maior faturamento entre os estados analisados, com **R$ 1.882.704**, seguido por **Maranhão (MA)**, com R$ 1.306.470.

---

### Quantidade de vendas por estado

A quantidade de vendas distintas foi analisada agrupando os registros por estado.

Os estados com maior volume de vendas foram:

* RO
* MA
* PR
* MG
* SC
* PA
* RR

Esses estados concentram os maiores volumes observados na análise de vendas por localização.

---

### Desempenho das lojas

A análise foi realizada utilizando o faturamento por loja, com ordenação decrescente.

As dez lojas com maior faturamento foram:

| Posição | Loja                           | Faturamento |
| ------: | ------------------------------ | ----------: |
|       1 | Capital Thrpy & Spts Medcn Inc |   R$ 39.559 |
|       2 | Rug Gallery                    |   R$ 34.199 |
|       3 | Berry, John M Esq              |   R$ 33.094 |
|       4 | Goodfellow Agency              |   R$ 32.241 |
|       5 | J C S Machinery                |   R$ 32.200 |
|       6 | Mnpls Arprt Marriott           |   R$ 31.359 |
|       7 | Barajas & Bustamante Archl     |   R$ 30.486 |
|       8 | Bomarko Inc                    |   R$ 29.519 |
|       9 | Inter American Press Assn      |   R$ 29.244 |
|      10 | Sheraton Inn Ocean Front       |   R$ 28.795 |

A loja **Capital Thrpy & Spts Medcn Inc** apresentou o maior faturamento entre as lojas analisadas, com aproximadamente **R$ 39,6 mil**.

---

## 5. Canais de venda

### Quantidade de vendas por canal

A quantidade de vendas distintas foi analisada agrupando os registros de acordo com o canal da loja.

| Canal                | Quantidade de Vendas |
| -------------------- | -------------------: |
| Franquia             |                3.032 |
| Loja local           |                2.057 |
| Supermercado         |                1.702 |
| Loja de rede pequena |                1.600 |

O canal **Franquia** apresentou o maior volume de vendas, com **3.032 vendas distintas**.

---

### Faturamento por canal

O faturamento foi analisado de acordo com o canal da loja.

| Canal                |  Faturamento |
| -------------------- | -----------: |
| Franquia             | R$ 2.542.290 |
| Loja local           | R$ 1.759.661 |
| Supermercado         | R$ 1.414.379 |
| Loja de rede pequena | R$ 1.367.824 |

O canal **Franquia** apresentou o maior faturamento e também o maior volume de vendas.

Esse resultado indica que o canal possui a maior contribuição para o desempenho comercial entre os canais analisados.

---

## 6. Devoluções

### Devoluções por categoria

A quantidade de registros de devolução foi analisada agrupando os registros por categoria de produto.

| Categoria     | Registros de Devolução |
| ------------- | ---------------------: |
| Moletom       |                    157 |
| Camisetas     |                     96 |
| Jaquetas      |                     84 |
| Calças        |                     81 |
| Regatas       |                     50 |
| Shorts        |                     45 |
| Sutiãs e Tops |                     33 |
| Em branco     |                      2 |
| **Total**     |                **548** |

A categoria **Moletom** apresentou a maior quantidade de registros de devolução, com **157 ocorrências**.

---

### Devoluções por estado

A quantidade de registros de devolução foi analisada agrupando os registros por estado.

| Estado | Devoluções |
| ------ | ---------: |
| RO     |        137 |
| MA     |         94 |
| PR     |         69 |
| MG     |         69 |
| SC     |         41 |
| RR     |         39 |
| PA     |         36 |
| ES     |         14 |
| RJ     |         10 |
| RS     |          8 |
| PI     |          7 |
| CE     |          6 |
| AM     |          5 |
| BA     |          5 |
| AP     |          4 |
| TO     |          3 |

Também foi identificado **1 registro com estado em branco**.

O estado de **Rondônia (RO)** apresentou a maior quantidade de registros de devolução, com **137 ocorrências**.

Esse resultado representa volume absoluto de devoluções e não necessariamente a maior taxa proporcional de devolução entre os estados.

---

### Taxa de devolução

A taxa de devolução foi calculada considerando a quantidade de **vendas distintas que possuem registro de devolução** em relação à quantidade total de vendas distintas.

**Medida utilizada:**

```DAX
% Devolução =
DIVIDE(
    [Devoluções],
    [Quantidade de Vendas]
)
```

Onde:

* `[Devoluções]` = quantidade de `Venda_id` distintos presentes na tabela `Devolução`;
* `[Quantidade de Vendas]` = quantidade de `Venda_id` distintos presentes na tabela `Vendas`.

O resultado observado foi:

**Taxa de devolução: 6,29%**

Esse indicador representa a proporção de vendas distintas que possuem registro de devolução.

A análise de registros de devolução apresenta **548 registros**, enquanto a medida utilizada para a taxa considera **528 vendas distintas com devolução**. Essa diferença ocorre porque uma mesma venda pode possuir mais de um registro na tabela `Devolução`.

---

## 7. Principal pergunta do Head

### Quais tipos de roupas são mais vendidos em cada estado?

Para responder à pergunta do Head, foi utilizada uma matriz com:

* **Linhas:** `Lojas[Estado]`
* **Colunas:** `Produtos[Produto_Categoria]`
* **Valores:** `[Quantidade de Produtos Vendidos]`

A utilização dessa medida permite analisar o **volume de unidades comercializadas**, diferenciando-o da quantidade de vendas distintas.

Os registros com categoria em branco foram mantidos identificados como dados sem classificação e não foram considerados uma categoria de produto.

O principal resultado observado foi que a categoria **Moletom** apresentou o maior volume de unidades vendidas em **15 dos 17 estados analisados**.

Com exceções nos estados do **Acre (AC)**, onde **Calças** apresentaram o maior volume, com **146 unidades vendidas**, contra **143 unidades de Moletom** e **Amapá (AP)** onde **Camisetas** apresentaram o maior volume, com **532 unidades vendidas**, contra **416 unidades de Moletom**

Os maiores volumes de unidades vendidas de Moletom foram observados em:

| Estado | Unidades de Moletom |
| ------ | ------------------: |
| RO     |                 626 |
| MA     |                 417 |
| PR     |                 288 |
| MG     |                 224 |
| SC     |                 186 |
| RR     |                 156 |
| PA     |                 152 |

O resultado demonstra que o **Moletom é a categoria predominante na maioria dos estados analisados**, sendo o principal destaque para a pergunta de negócio definida pelo Head.

---

## 8. Principais descobertas

Durante a análise exploratória, foram identificados os seguintes pontos:

### 8.1 Predominância do Moletom

A categoria **Moletom** foi a mais vendida em **15 dos 17 estados analisados**, considerando o volume de unidades comercializadas.

No total da base, foram identificadas **59.102 unidades de Moletom vendidas**.

### 8.2 Exceções no Acre e Amapá

No estado do **AP**, a categoria mais vendida foi **Camisetas**, com **532 unidades**, contra **416 unidades de Moletom**.
No estado do **AC**, a categoria mais vendida foi **Calças**, com **146 unidades**, contra **143 unidades de Moletom**.

### 8.3 Maior faturamento por categoria

A categoria **Moletom** apresentou o maior faturamento, com **R$ 1.931.691**.

### 8.4 Produtos de maior faturamento

O produto **Hyperion EleMasculinots Jaqueta** apresentou o maior faturamento individual, com aproximadamente **R$ 207,4 mil**.

### 8.5 Desempenho dos canais

O canal **Franquia** apresentou simultaneamente o maior volume de vendas e o maior faturamento.

### 8.6 Desempenho por estado

**Rondônia (RO)** apresentou o maior faturamento entre os estados analisados, com **R$ 1.882.704**.

### 8.7 Devoluções por categoria

A categoria **Moletom** apresentou a maior quantidade de registros de devolução, com **157 ocorrências**.

### 8.8 Devoluções por estado

O estado de **Rondônia (RO)** apresentou a maior quantidade absoluta de registros de devolução, com **137 ocorrências**.

### 8.9 Taxa de devolução

A taxa de devolução, considerando vendas distintas com devolução, foi de **6,29%**.

### 8.10 Comportamento temporal

O maior faturamento mensal foi observado em **maio de 2021**, enquanto o menor ocorreu em **dezembro de 2021**, após validação da completude dos dias do mês.

### 8.11 Qualidade dos dados

Foram identificados registros com valores em branco em diferentes dimensões, incluindo produto, categoria e estado.

Esses registros foram mantidos identificados durante a análise para evitar a perda de informação e devem ser considerados nas avaliações de qualidade dos dados.

---

## 9. Conclusão

A análise exploratória permitiu identificar padrões relevantes de vendas, faturamento, canais, localização e devoluções.

Os principais resultados indicam:

* **Moletom** como principal categoria em volume de unidades vendidas na maioria dos estados;
* **59.102 unidades de Moletom** comercializadas na base;
* **Moletom** também como categoria de maior faturamento;
* **Franquia** como principal canal em quantidade de vendas e faturamento;
* **RO** como estado de maior faturamento;
* **Hyperion EleMasculinots Jaqueta** como produto de maior faturamento individual;
* **RO** como estado com maior quantidade absoluta de registros de devolução;
* **Moletom** como categoria com maior quantidade de registros de devolução;
* **6,29%** como taxa de devolução considerando vendas distintas com devolução;
* **maio de 2021** como mês de maior faturamento;
* **dezembro de 2021** como mês de menor faturamento, após validação da completude dos dias do mês;
* existência de registros com informações em branco que devem ser considerados na análise de qualidade dos dados.

A principal pergunta de negócio também foi respondida: **Moletom lidera em 15 dos 17 estados analisados. As exceções são Acre (AC), onde Calças lidera com 146 unidades contra 143 de Moletom, e Amapá (AP), onde Camisetas lidera com 532 unidades contra 416 de Moletom.**

Esses resultados fornecem uma visão consolidada do comportamento comercial da base e servem como fundamento para a apresentação dos indicadores e recomendações de negócio no dashboard final.
