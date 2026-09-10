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
## Funçoes de agregação 

Funções de agregação realizam calculos ou processos em registros de um resultado.
Entre as principais:

- `COUNT()` -> conta registros 
- `SUM()` -> soma valores
- `AVG()` -> calcula a média de valores
- `MIN()` -> encontra menor valor
- `MAX()` -> encontra maior valor
- `ROUND()` -> arredonda valores e define casas decimais 

### COUNT
contando quantos registros existem na tabela produtos
```sql
SELECT  COUNT(*) AS total FROM produtos;
```

### SUM
Somar a quantidade de todos os produtos da tabela:
```sql
SELECT  SUM(quantidade) AS "Quantidade total" FROM produtos;
```
### AVG
Calcular a media dos preços dos produtos:
```sql
SELECT  AVG(preco) AS "Média dos preços" FROM produtos;
```
### MIN
Retornar ao menor preco existente
```sql
SELECT  MIN(preco) AS menor_preco FROM produtos;
```

### MAX
Retornar ao maior preco existente:
```sql
SELECT  MAX(preco) AS maior_preco FROM produtos;
```

### COMBINANDO AGREGAÇÕES

```sql
SELECT  COUNT(*) AS quantidades_produtos,
        MIN(preco) AS menor_preco,
        MAX(preco) AS maior_preco,
        ROUND(AVG(preco),2) AS preco_medio
FROM produtos;
```
**ATENÇÃO** Não coloque espaço entre o nome da função e os parenteses!

## Recursos de agrupamento
 
`GROUP BY` reune registros que possuem um determinado valor me comum.

### Contando produtos de fornecedor
 ```sql
SELECT fornecedor_id, COUNT(*) AS total_produtos
FROM produtos GROUP BY fornecedor_id;
```
### Determinando a média de preços por fornecedor
 ```sql
SELECT fornecedor_id, ROUND(AVG(preco) , 2) AS preco_medio
FROM produtos GROUP BY fornecedor_id;
```
### HAVING
 
`HAVING` permite filtrar os grupos criados pelo `GROUP BY`.
**obs:** para usar o HAVING **precisa ter** GRUP BY

Exemplo: mostrar somente os fornecedores que possuem pelo menos dois produtos cadastrados
 ```sql
SELECT fornecedor_id, COUNT(*) AS total_produtos
FROM produtos GROUP BY fornecedor_id
HAVING COUNT(*) >= 2;
```
### Combinando WHERE, GROUP BY, HAVING e ORDER BY
Objetivos:
1. Considera produtos com quantidade maior que zero
2. Agrupa por fornecedor
3. Calcula a quantidade e preço médio de cada grupo
4. Mantém apenas fornecedores com pelo menos dois produtos
5. Ordena os grupos pelo preço médio

 ```sql
SELECT 
     fornecedor_id, 
     COUNT(*) AS total_produtos,
     ROUND(AVG(preco) , 2) AS preco_medio
FROM produtos 
WHERE quantidade > 0
GROUP BY fornecedor_id
HAVING total_produtos >= 2
ORDER BY preco_medio DESC;
```
**obs:** ao combinar os produtos a ordem deve ser :
1. WHERE
2. GROUP BY/HAVING
3. ORDER BY


