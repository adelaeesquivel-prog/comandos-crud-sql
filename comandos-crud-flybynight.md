# Comandos CRUD para o banco de dados Fly By Night
 
##  INSERT da tabela de fornecedor
 
```sql
INSERT INTO fornecedores(nome) VALUES ('Eletronicos trabajara');

INSERT INTO fornecedores(nome) VALUES 
    ('Games ABCD'),
    ('Supermercado Tem de Tudo'),
    ('Livraria Demais da Conta');
```

##  INSERT da tabela Produtos
```sql
INSERT INTO produtos(nome,descricao,preco,quantidade,fornecedor_id) 
VALUES (
    'Smatphone Galaxy S23',
    'Equipamento com Sistema Android e camera Full HD e etc e tal',
    1599.45,
    20,
    1 -- id do fornecedor eletronicos trabajara
);

INSERT INTO produtos(nome,descricao,preco,quantidade,fornecedor_id) 
VALUES (
    'Senhor dos Aneis:As duas Torres',
    'Volume 2 da serie livros criados pelo autor J.R.R Tolkeien',
    80.99,
    100,
    4 -- id do fornecedor eletronicos trabajara
    );

INSERT INTO produtos (nome, descricao, preco, quantidade, fornecedor_id)
VALUES (
    'TV led',
    'Tela de 50 polegadas, resolução 4k, 4 entradas HDMI',
     3420,
     12,
      1 -- id fornecedor eletronico tabajara
);

```
##  INSERT da tabela lojas
```sql
INSERT INTO lojas (nome) 
VALUES 
    ('Casas Bahia'),
    ('Shopping Zona Leste'),
    ('Bazar das coisas'),
    ('Americanas');
```
##  INSERT da tabela Lojas-Produtos

esta é uma tabelaintermediaria(tambem conhecida como **Tabela Pivot**), ou seja , ela se relaciona com outras duas tabelas: **produtos** e **lojas** atraves de chaves estrangeiras.
```sql
INSERT INTO lojas_produtos (loja_id ,produto_id, estoque) VALUES (2, 1 ,20);

INSERT INTO lojas_produtos (loja_id ,produto_id, estoque) VALUES (4, 2 ,3);
INSERT INTO lojas_produtos (loja_id ,produto_id, estoque) VALUES (2, 3 ,10);
INSERT INTO lojas_produtos (loja_id ,produto_id, estoque) VALUES (1, 1 ,5);
INSERT INTO lojas_produtos (loja_id ,produto_id, estoque) VALUES (4, 1 ,2);

```
---

## UPDATE  na tabela fornecedores
```sql
UPDATE fornecedores SET nome = 'Mundo dos Games'
WHERE id = 2;
```

## UPDATE  na tabela produtos 
```sql
UPDATE produtos SET preco = 2999, quantidade = 5 WHERE id = 3;
```

## UPDATE  na tabela lojas_produtos 
```sql
UPDATE lojas_produtos SET estoque = 4 WHERE loja_id = 2 AND produto_id = 1;

-- SQL aceita operadores logicos: AND (E), OR (OU),NOT(NAO)

```
 
