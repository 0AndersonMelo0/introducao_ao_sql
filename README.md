# Resolução exercício SQL

1ª Abra o arquivo ´tabela_paises.txt´ acima e copie e cole no SGBD PostgreSQL.

## 1ª Questão:
Selecione todos os dados dos países da tabela_paises;

<h5>Code:</h5>

```sql
select id_nf, id_item, cod_prod, valor_unit 
from produtos
where desconto is null;
```
## Output:
