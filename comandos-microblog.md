## CATEGORIAS
```sql
INSERT INTO categorias (nome) VALUES 
    ('Tecnologia'),
    ('Educação'),
    ('Entretenimento');
```

## USUARIOS
```sql
INSERT INTO usuarios(nome,email,senha,tipo) 
VALUES (
    'Ana Silva',
    'ana@email.com',
    '123abc' ,
    'editor'
);

INSERT INTO usuarios(nome,email,senha,tipo) 
VALUES (
    'Bruno Souza',
    'bruno@email.com',
    'abc456' ,
    'admin'
);

INSERT INTO usuarios(nome,email,senha,tipo) 
VALUES (
    'Carla Mendes',
    'carla@email.com',
    '789xyz' ,
    'editor'
);
```

## NOTICIAS
```sql
INSERT INTO noticias(titulo,resumo,texto,imagem, destaque,usuario,categoria) 
VALUES (
    'Escolas adotam realidade virtual para aulas de ciência',
    'Alunos agora exploram o corpo humano e o espaço em simulações 3D interativas.',
    'Redes de ensino começaram a implementar óculos de realidade virtual no cotidiano escolar. A tecnologia permite que os estudantes façam passeios virtuais pelo sistema solar e explorem estruturas celulares de forma imersiva. A iniciativa busca aumentar o engajamento e facilitar o aprendizado de conceitos abstratos.' ,
    'rv_educacao_sala_de_aula.jpg',
    'sim',
    1,
    categoria:tecnologia


);
```
