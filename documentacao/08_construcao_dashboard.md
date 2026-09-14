# Construção do Dashboard

## Objetivo

Após o planejamento da estrutura do dashboard, foram construídas as quatro páginas definidas na etapa anterior, utilizando o Power BI.

A construção priorizou clareza, consistência visual, facilidade de exploração e apresentação objetiva dos principais indicadores de desempenho.

## Página 1 — Visão Executiva

A página foi construída para apresentar uma visão geral do desempenho comercial.

### Indicadores

* Faturamento;
* Quantidade de Vendas;
* Quantidade de Produtos Vendidos;
* Lucro;
* Margem;
* Percentual de Devolução.

### Análises

* Faturamento por Ano-Mês;
* Faturamento por Categoria;
* Faturamento por Estado.

### Filtros

* Período;
* Estado;
* Canal;
* Categoria.

A página funciona como uma visão inicial do desempenho do negócio, permitindo identificar rapidamente os principais resultados e explorar os dados por meio dos filtros.

## Página 2 — Produtos e Vendas

A segunda página foi construída com foco em produtos, volume de vendas e canais comerciais.

### Indicadores

* Quantidade de Vendas;
* Quantidade de Produtos Vendidos;
* Faturamento;
* Ticket Médio.

### Análises

* Quantidade de Produtos Vendidos por Categoria;
* Faturamento por Canal;
* Top 10 Faturamentos por Nome do Produto;
* Quantidade de Vendas por Canal.

### Filtros

* Período;
* Estado;
* Canal;
* Categoria.

A página permite comparar o desempenho dos canais e identificar categorias e produtos de maior relevância comercial.

## Página 3 — Análise Geográfica

A terceira página foi construída para analisar diferenças de desempenho entre os estados.

### Indicadores

* Faturamento;
* Lucro;
* Margem;
* Quantidade de Vendas;
* Quantidade de Produtos Vendidos.

### Análises

* Faturamento por Estado;
* Margem por Estado;
* Quantidade de Produtos Vendidos por Estado;
* Quantidade de Produtos Vendidos por Estado e Categoria.

A matriz de Estado × Categoria permite detalhar quais categorias apresentam maior volume em cada estado.

### Filtros

* Período;
* Estado;
* Canal;
* Categoria.

## Página 4 — Devoluções

A quarta página foi construída especificamente para analisar o comportamento das devoluções.

### Indicadores

* Registros de Devolução;
* Devoluções por vendas distintas;
* Quantidade de Vendas;
* Percentual de Devolução.

Foi mantida a distinção entre registros e vendas distintas:

* **548 registros de devolução** correspondem à quantidade de linhas existentes na tabela `Devolução`;
* **528 devoluções** correspondem à quantidade de `Venda_id` distintos que apresentaram devolução.

Essa distinção permite preservar o volume real de registros e, ao mesmo tempo, identificar a quantidade de vendas afetadas.

### Análises

* Evolução dos Registros de Devolução;
* Top 10 Produtos por Registros de Devolução;
* Registros de Devolução por Estado;
* Registros de Devolução por Categoria.

### Filtros

* Período;
* Estado;
* Canal;
* Categoria.

## Interatividade

Os segmentadores foram configurados para permitir a análise dos dados de acordo com diferentes períodos, estados, canais e categorias.

Após a construção, foram realizados testes de interação entre filtros, indicadores e visuais para verificar se os resultados eram atualizados corretamente.

## Padronização Visual

As quatro páginas foram construídas mantendo uma identidade visual consistente.

Foram utilizados:

* fundo escuro;
* cartões com destaque para os principais indicadores;
* gráficos com padrão visual consistente;
* títulos objetivos;
* distribuição organizada dos elementos;
* segmentadores posicionados de forma padronizada;
* formatação numérica adequada a cada indicador.

## Validação Final

Após a construção, as quatro páginas foram revisadas individualmente.

Foram verificados:

* funcionamento dos filtros;
* interação entre os visuais;
* ordenação dos gráficos;
* formatação dos valores;
* consistência dos indicadores;
* legibilidade;
* posicionamento dos elementos;
* ausência de sobreposição entre os visuais.

Com essa revisão, o dashboard foi considerado concluído e pronto para apresentação.
