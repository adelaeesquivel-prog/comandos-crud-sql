## Consulte todos os dados de todos os usuários cadastrados.
```sql
SELECT * FROM usuarios;
```
## Consulte apenas algumas informações dos usuários, como nome e e-mail (ou colunas equivalentes existentes no seu banco).
```sql
SELECT nome, email FROM usuarios;
```

## Consulte os dados das categorias cadastradas.
```sql
SELECT * FROM categorias;
```

## Consulte apenas algumas informações das notícias, como título e data de publicação.
```sql
SELECT titulo, data FROM noticias;
```

## Faça uma consulta utilizando AS para alterar o nome de pelo menos duas colunas no resultado.
```sql
SELECT
    nome AS identificação,
    email AS correio_eletronico
FROM usuarios;
```

## Consulte somente os usuários de um determinado tipo, de acordo com os dados existentes no seu banco.
```sql
SELECT * FROM usuarios WHERE tipo = 'admin';
```

## Consulte somente as notícias que estejam marcadas como destaque (ou alguma informação equivalente existente no seu modelo).
```sql
SELECT * FROM noticias WHERE  destaque = 'sim';
```

## Escolha uma categoria existente no seu banco e consulte as notícias pertencentes a ela utilizando seu identificador.
```sql
SELECT id,titulo,resumo,data,categoria_id
FROM noticias 
WHERE categoria_id=2;
```

## Faça uma consulta utilizando o operador <> para excluir do resultado algum tipo de usuário, categoria ou outro valor existente no seu banco.
```sql
SELECT nome, email, tipo FROM usuarios WHERE tipo <> 'admin';
```
## Faça uma consulta utilizando AND para estabelecer duas condições simultaneamente.
```sql
SELECT id,titulo,resumo,data,categoria_id FROM noticias
WHERE destaque = 'sim' AND categoria_id = 4 ;
```
## Faça outra consulta utilizando OR, na qual um registro possa aparecer se atender a uma condição ou outra.
```sql
SELECT nome , email, senha, tipo FROM usuarios
WHERE nome = 'Junior ALVAREZ OR categoria_id = 2;
```