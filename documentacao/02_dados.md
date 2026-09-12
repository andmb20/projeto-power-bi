# Estrutura e Tratamento dos Dados

## 1. Fontes de dados

O projeto utiliza quatro tabelas provenientes de arquivos Excel:

* Vendas
* Produtos
* Lojas
* Devolução

---

## 2. Validação dos dados

A validação foi realizada no Power Query utilizando as funcionalidades de distribuição de colunas, qualidade da coluna e visualização de valores em branco.

Foram verificados:

* tipos de dados;
* valores nulos/vazios;
* erros;
* valores distintos e exclusivos;
* possíveis duplicidades;
* chaves das tabelas;
* coerência dos valores;
* campos de data e valores numéricos.

### 2.1 Produtos

**Chave:** `Produto_SKU`

Resultados:

* 1.210 valores distintos;
* 1.210 valores exclusivos;
* `Produto_SKU` é único na tabela;
* `Produto_Descrição` também apresenta 1.210 valores distintos e 1.210 exclusivos;
* 0% de erros;
* 0% de valores vazios;
* 100% de valores válidos.

**Tratamento realizado:**

* Primeira linha promovida a cabeçalho.
* Nenhuma outra transformação necessária.

---

### 2.2 Vendas

**Chave:** `Venda_id`

Resultados:

* 8.391 valores distintos;
* 8.391 valores exclusivos;
* `Venda_id` é único na tabela;
* 0% de erros;
* 0% de valores vazios;
* 100% de valores válidos.

**Tipos de dados avaliados:**

* `Venda_data` → Date;
* campos monetários → Número decimal;
* `Venda_id` → inteiro;
* `Produto_sku` e `Loja_id` → tipos compatíveis com os relacionamentos do modelo.

**Tratamento realizado:**

* Nenhuma transformação adicional foi necessária.

---

### 2.3 Lojas

**Chave:** `Loja_id`

Resultados:

* `Loja_id` apresenta quantidade de valores distintos igual à quantidade de valores exclusivos e ao total de registros;
* `Loja_id` é único na tabela;
* 0% de erros;
* 0% de valores vazios;
* 100% de valores válidos.

Foram identificados casos em que nomes de lojas podem se repetir entre diferentes registros. Esses registros não foram considerados duplicados porque possuem `Loja_id` distintos e podem representar estabelecimentos diferentes, inclusive em canais diferentes.

**Tratamento realizado:**

* Nenhuma remoção de registros.
* Nenhuma transformação adicional necessária.

---

### 2.4 Devolução

**Chave de relacionamento:** `Venda_id`

Resultados:

* 548 registros;
* 528 valores distintos de `Venda_id`;
* 509 valores exclusivos;
* 0% de erros;
* 0% de valores vazios;
* 100% de valores válidos.

A existência de valores repetidos em `Venda_id` foi mantida, pois uma mesma venda pode possuir múltiplos registros relacionados à devolução.

**Tipos de dados:**

* `Devolução_data` → Date;
* `Venda_id` → inteiro;
* `Devolução_ano` → inteiro;
* `Devolução_mes` → inteiro;
* `Devolução_dia` → inteiro;
* `Hora` → inteiro;
* `Minuto` → inteiro;
* `Segundo` → inteiro.

**Tratamento realizado:**

O campo `Devolução_mes_1` foi renomeado para `Devolução_dia`, pois a análise dos dados indicou que o campo representa o dia do mês da devolução.

Nenhum registro foi removido.

---

## 3. Relacionamentos validados

Os relacionamentos identificados no modelo são:

```text
Produtos[Produto_sku]  1 ─── * Vendas[Produto_sku]

Lojas[Loja_id]        1 ─── * Vendas[Loja_id]

Vendas[venda_id]      1 ─── * Devolução[Venda_id]
```

As cardinalidades foram verificadas na Exibição de Modelo do Power BI.

---

## 4. Conclusão da etapa de tratamento

Os dados apresentaram boa qualidade estrutural.

Não foram identificados erros, valores vazios ou duplicidades indevidas que justificassem exclusão ou correção dos registros.

As principais decisões de tratamento foram:

1. Promover a primeira linha a cabeçalho na tabela Produtos;
2. Renomear `Devolução_mes_1` para `Devolução_dia`;
3. Manter registros repetidos de `Venda_id` na tabela Devolução;
4. Manter lojas com nomes semelhantes ou iguais quando possuem `Loja_id` diferentes;
5. Preservar os tipos de dados já adequados;
6. Não realizar transformações desnecessárias.
