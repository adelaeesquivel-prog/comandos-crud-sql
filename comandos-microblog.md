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

## CATEGORIAS
```sql
INSERT INTO categorias (nome) VALUES 
    ('Tecnologia'),
    ('Educação'),
    ('Entretenimento');
```

## NOTICIAS

# NOTICIA 1
```sql
INSERT INTO noticias(titulo,resumo,texto,imagem, destaque,usuario_id,categoria_id) 
VALUES (
    'Escolas adotam realidade virtual para aulas de ciência',
    'Alunos agora exploram o corpo humano e o espaço em simulações 3D interativas.',
    'Redes de ensino começaram a implementar óculos de realidade virtual no cotidiano escolar. A tecnologia permite que os estudantes façam passeios virtuais pelo sistema solar e explorem estruturas celulares de forma imersiva. A iniciativa busca aumentar o engajamento e facilitar o aprendizado de conceitos abstratos.' ,
    'rv_educacao_sala_de_aula.jpg',
    'sim',
    1,
    1
);
```

# NOTICIA 2
```sql
INSERT INTO noticias(titulo,resumo,texto,imagem, destaque,usuario_id,categoria_id) 
VALUES (
    'Festival de cinema independente bate recorde de público e arrecadação',
    'Evento reuniu mais de 100 produções internacionais e premiou diretores estreantes.',
    'A 15ª edição do festival encerrou no último domingo com público recorde de 80 mil pessoas. O grande vencedor da noite foi um longa-metragem gravado inteiramente via smartphone, destacando o crescimento do cinema de baixo orçamento.' ,
    'ent_festival.jpg ',
    'nao',
    2,
    3
);
```

# NOTICIA 3
```sql
INSERT INTO noticias(titulo,resumo,texto,imagem, destaque,usuario_id,categoria_id) 
VALUES (
    'Plataforma gratuita de tutoria por IA é liberada para estudantes da rede pública',
    'Ferramenta tira dúvidas de matemática e redação 24 horas por dia com acompanhamento pedagógico.',
    ' O Ministério da Educação lançou um assistente virtual adaptativo para alunos do ensino médio. A ferramenta identifica as principais dificuldades de cada estudante em tempo real, gerando exercícios personalizados e relatórios semanais de desempenho para os professores da turma.' ,
    'edu_tutoria_ia.jpg ',
    'nao',
    3,
    2
);
```

# NOTICIA 4
```sql
INSERT INTO noticias(titulo,resumo,texto,imagem, destaque,usuario_id,categoria_id) 
VALUES (
    'Adaptação de jogo clássico quebra recordes de bilheteria no fim de semana',
    'Filme supera expectativas e se torna a maior estreia do ano nos cinemas mundiais.',
    'A nova produção cinematográfica baseada na famosa franquia de videogames arrecadou mais de US$ 200 milhões em seu primeiro final de semana. A crítica destacou a fidelidade ao material original e os efeitos visuais como os principais pontos fortes da obra.' ,
    'ent_cinema.jpg  ',
    'sim',
    1,
    3

);
```

## UPDATE  na tabela fornecedores
```sql
UPDATE fornecedores SET nome = 'Mundo dos Games'
WHERE id = 2;
```

## DELETE na tabela fornecedores
```sql
DELETE FROM fornecedores WHERE id = 5;
```



