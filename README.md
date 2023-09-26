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
<img src="https://github.com/0AndersonMelo0/introducao_ao_sql/assets/111611117/b67bd6f5-d536-40fa-924b-9eeacfe29e2b">

(deverá aparecer algo próximo a isso, só que com 500 entidades)

<hr>

## 2ª Questão:
Selecione todas as cidades cujo país seja brazil;

```sql
select cidade from tabela_paises where pais='Brazil';
```
<h4>Output:</h4>
<img src="https://github.com/0AndersonMelo0/introducao_ao_sql/assets/111611117/c28a8d6e-3eba-4562-bc5a-7b7c2ab0e5ec">
(ao todo são 21 cidades diferentes)

<hr>

## 3ª Questão:
Selecione todas as cidades cuja região(estado) é ceará;

```sql
select cidade from tabela_paises where regiao='Ceará';
```
<h4>Output:</h4>
<img src="https://github.com/0AndersonMelo0/introducao_ao_sql/assets/111611117/a669b8e8-01c1-443d-b615-b16674a3c75a")>
(há apenas duas cidades)

<hr>

## 4ª Questão:
Utilize a função <b>count</b> para saber quantas regiões(estados) existem na China,
utilize também o <b>group by</b>;

```sql
select count(*) as quant, regiao from tabela_paises where pais='China' group by regiao;
select count(distinct regiao) as quant_total from tabela_paises where pais='China';
```
<h4>Output:</h4>
<img src="https://github.com/0AndersonMelo0/introducao_ao_sql/assets/111611117/49d28f3e-5d42-4d70-8677-c9f3ade10f2a">

<hr>

## 5ª Questão:
Quais regiões, diferentes, existem no Canadá?

```sql
select count(*) as quant, regiao from tabela_paises where pais='Canada' group by regiao;
```
<h4>Output:</h4>

<img src="https://github.com/0AndersonMelo0/introducao_ao_sql/assets/111611117/da82d937-6631-4bb1-8b35-3e2ee425b35c">
<img src="https://github.com/0AndersonMelo0/introducao_ao_sql/assets/111611117/8cc93d97-5f85-4dba-affa-ea693bcab7d9">

<hr>

## 6ª Questão:
Quantos países diferentes existem na tabela 'tabela_paises';

```sql
select count(distinct pais) from tabela_paises;
```
<h4>Output:</h4>
<img src="https://github.com/0AndersonMelo0/introducao_ao_sql/assets/111611117/ad21927e-ebc4-4d26-9a2c-45b069e97d8d">

<hr>

## 7ª Questão:
Quantas cidades diferentes existem no brazil;

```sql
select count(distinct cidade) from tabela_paises where pais='Brazil';
```
<h4>Output:</h4>
(igual mente como a Q6 só que devera retornar: 21)

<hr>

## 8ª Questão:
Selecione os países e quantas regiões cada país possui;

```sql
select count(distinct regiao) as quant_regiao, pais from tabela_paises group by pais;
```
<h4>Output:</h4>
<img src="https://github.com/0AndersonMelo0/introducao_ao_sql/assets/111611117/5cc04d0b-91fd-48b7-ae57-7e428ca6c700">
<img src="https://github.com/0AndersonMelo0/introducao_ao_sql/assets/111611117/e86619ea-eb44-4a92-aa51-e4f7cc458d77">
<img src="https://github.com/0AndersonMelo0/introducao_ao_sql/assets/111611117/48aa2468-c5ba-4c06-a8a2-62ca4ae776a0">

<hr>
## 9ª Questão:
Quantas pessoas com nome começando em 'João' existem no banco?

```sql
select count(nome) as quant_Jaoa from tabela_paises where nome like 'João%';
```
<h4>Output:</h4>
(igual a saída da Q6, só que devera retornar: 0)

<hr>
## 10ª Questão:
Quantas pessoas têm o nome John?

```sql
select count(nome) as qunt_Jonh, nome from tabela_paises where nome like 'John%';
```
<h4>Output:</h4>
<img src="https://github.com/0AndersonMelo0/introducao_ao_sql/assets/111611117/5b5f236e-dfc1-4809-ac5b-0dd67c221725">

<hr>
## 11ª Questão:
Ordene os nomes dos países sem repetição em ordem alfabética;

```sql
select pais from tabela_paises group by pais order by pais;
```
<h4>Output:</h4>
(igual a saída da Q8, só que em ordem alfabética e sem a coluna quant_regiao)
