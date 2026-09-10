# SQL SLECT - Exemplos consultas ao banco de Fly By Night

O comando `SELECT` é usado para **consultar dadaos armazenados nas tabelas do  banco de dadodos**

## SELECT básico : consultar todos os dados de uma tabela

Consultar todos os dados de uma tabela:

```sql
SELECT * FROM produtos;
```

## SELECT para apenas determinadas colunas
```sql
SELECT nome, preco FROM produtos;
```

## Alterando o nome de exibição das colunas
usamos o comando `AS` para criar um **apelido (alias)**.

```sql
SELECT
    nome AS produto,
    preco AS valor
FROM produtos;
```

## Filtrando registros com WHERE
o `WHERE` permite detreminar **quais registros devem aparecer** no resultados. Na pratica, são condições para execução de `SELECT`.

### Comparação de igualdade
```sql
-- o * representa todas as colunas.
SELECT * FROM produtos WHERE quantidade = 0;
```

### Comparação de maior /menor
```sql
SELECT nome, preco FROM produtos WHERE preco > 1000;
```

### Comparação de menor ou igual
```sql
SELECT nome, preco FROM produtos WHERE preco <= 1000;
```
### Comparação de diferença
Normalmente se usa o operador `<>` em vez do `!=`.
```sql
SELECT * FROM produtos WHERE fornecedor_id <> 1;
```
---
## Combinando condições

usamos o `WHERE` e operadores lógicos e relacionais

### Operador AND (E)
exibir os produtos que custem menos de 500 e quantidade acima de 20.
```sql
SELECT nome, preco, quantidade FROM produtos
WHERE preco < 500 AND quantidade > 20 ;
```
### Operador OR (OU)
exibir os produtos que custem mais de 3000 ou com quantidade zerada.
```sql
SELECT nome, preco, quantidade FROM produtos
WHERE preco > 3000  OR quantidade = 0 ;
```

### Operador NOT (NÃO)
exibir os produtos que **não possuem preço acima de 1000**.
```sql
SELECT nome, preco, quantidade FROM produtos WHERE NOT  preco > 1000;  
```

**obs.:**  o uso do NOT não é obrigatorio , dede que voce consiga  o mesmo resultado usando uma logica diferente, como no exemplo: 
`SELECT nome, preco, quantidade FROM produtos WHERE  preco <= 1000;`

### BETWEEN

Exibir produtos com preço **entre 100 e 500**.
```sql
SELECT nome, preco  FROM produtos
WHERE  preco BETWEEN 100 AND 500;  
```
### IN

Exibir produtos que tenha o fornecedor ID 1, 4 ou 8.
```sql
SELECT * FROM produtos
WHERE  fornecedor_id IN (1, 4, 8);  
```
sem usar o `IN`, teriamos que fazer :
```sql
SELECT * FROM produtos
WHERE 
   fornecedor_id = 1 OR
   fornecedor_id = 4 OR
   fornecedor_id = 8;
```

### LIKE
`LIKE` é usado principalmente para realizar pesquisas em textos. Junto com o caractere `%` permite fazer buscas basadas em partes de uma string.
Exemplo: procurar produtos que tenham a palavra **Gamer** em qualquer posição do nome.
```sql
SELECT nome, preco FROM produtos
WHERE nome LIKE '%Gamer%';
```

## DISTINCT
Elimina valores repetidos do resultado de consulta.
```sql
SELECT DISTINCT fornecedor_id FROM produtos;
```

## ORDENAÇÃO (ou CLASSIFICAÇÃO)
usamos o `ORDER BY` para organizar os registros do resultado.

### Ordem crescente (padrão)
exemplos: do menor para o maior, ou de A-Z, de mais antigo para mais recente.
```sql
SELECT nome, preco FROM produtos
ORDER BY preco ASC;
-- nem precisa colocar o ASC, pois é padrão 
```

### Ordem decrescente 
exemplos: do maior para o menor, ou de Z-A, do  mais recente para o mais antigo  .
```sql
SELECT nome, preco FROM produtos
ORDER BY preco DESC;
```

### Ordenando por mais de uma coluna 

```sql
SELECT nome, preco FROM produtos
ORDER BY preco DESC, nome ASC;
```

