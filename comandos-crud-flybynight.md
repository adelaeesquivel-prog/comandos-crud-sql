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



 
