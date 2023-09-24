# Resolução exercício SQL

1ª Abra o arquivo ´tabela_paises.txt´ acima e copie e cole no SGBD PostgreSQL.
<hr>
## 1ª Questão:
Selecione todos os dados dos países da tabela_paises;

<h4>Code:</h4>

```sql
select * from tabela_paises;
```
<h4>Output:</h4>

<hr>
## 2ª Questão:
Selecione todas as cidades cujo país seja brazil;

```sql
select cidade from tabela_paises where pais='Brazil';
```
<h4>Output:</h4>

<hr>
## 3ª Questão:
Selecione todas as cidades cuja região(estado) é ceará;

```sql
select cidade from tabela_paises where regiao='Ceará';
```
<h4>Output:</h4>

<hr>
## 4ª Questão:
Utilize a função <b>count</b> para saber quantas regiões(estados) existem na China,
utilize também o <b>group by</b>;

```sql
select count(*) as quant, regiao from tabela_paises where pais='China' group by regiao;
select count(distinct regiao) as quant_total from tabela_paises where pais='China';
```
<h4>Output:</h4>

<hr>
## 5ª Questão:
Quais regiões, diferentes, existem no Canadá?

```sql
select count(*) as quant, regiao from tabela_paises where pais='Canada' group by regiao;
```
<h4>Output:</h4>

<hr>
## 6ª Questão:
Quantos países diferentes existem na tabela 'tabela_paises';

```sql
select count(distinct pais) from tabela_paises;
```
<h4>Output:</h4>

<hr>
## 7ª Questão:
Quantas cidades diferentes existem no brazil;

```sql
select count(distinct cidade) from tabela_paises where pais='Brazil';
```
<h4>Output:</h4>

<hr>
## 8ª Questão:
Selecione os países e quantas regiões cada país possui;

```sql
select count(distinct regiao) as quant_regiao, pais from tabela_paises group by pais;
```
<h4>Output:</h4>

<hr>
## 9ª Questão:
Quantas pessoas com nome começando em 'João' existem no banco?

```sql
select count(nome) as quant_Jaoa from tabela_paises where nome like 'João%';
```
<h4>Output:</h4>

<hr>
## 10ª Questão:
Quantas pessoas têm o nome John?

```sql
select count(nome) as quant_Jaoa, nome from tabela_paises where nome like 'John%' group by nome;
```
<h4>Output:</h4>

<hr>
## 11ª Questão:
Ordene os nomes dos países sem repetição em ordem alfabética;

```sql
select pais from tabela_paises group by pais order by pais;
```
<h4>Output:</h4>
