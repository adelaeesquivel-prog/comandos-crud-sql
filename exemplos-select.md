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