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