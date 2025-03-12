# Comandos para o exercício 

## Criando as tabelas
### PROFESSOR, CURSO E ALUNO


#### Criando a tabela CURSO
``` sql
CREATE TABLE curso (
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nomedocurso VARCHAR(200) NOT NULL,
    cargahoraria INT NOT NULL,
    professor_id INT NOT NULL,   
);
```

#### Criando a tabela PROFESSOR
``` sql
CREATE TABLE professor (
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nomedoprofessor VARCHAR(200) NOT NULL,
    areadeatuacao ENUM('Design', 'Desenvolvimento', 'Infra') NOT NULL,
    curso_id INT NOT NULL  
);
```

#### Criando a tabela ALUNO
``` sql
CREATE TABLE aluno (
    id INT NOT NULL PRIMARY KEY AUTO_INCREMENT,
    nomedoaluno VARCHAR(200) NOT NULL,
    datadenascimento DATE NOT NULL,
    primeiranota INT NOT NULL,
    segundanota INT NOT NULL,
    curso_id INT NOT NULL,   
);
```

#### Adicionando os cursos e a cargahoraria
```sql
INSERT INTO curso (nomedocurso, cargahoraria) VALUES
(
    'Front-End',
    40
),
(
    'Back-End',
    80
),
(
    'UX/UI Design',
    30
),
(
    'Figma',
    10
),
(
    'Redes de Computadores',
    100
);
```

#### Adicionando os professores, a area de atuação e o curso que ele dá aula
```sql
INSERT INTO professor (nomedoprofessor, areadeatuacao, curso_id) VALUES
(
    'Jon Oliva',
    'Infra',
    5
),
(
    'Lemmy Kilmister',
    'Design',
    4
),
(
    'Neil Peart',
    'Design',
    3
),
(
    'Ozzy Osbourne',
    'Desenvolvimento',
    2
),
(
    'David Gilmour',
    'Desenvolvimento',
    1
);
```

#### Adiconando os alunos (""""cadastro deles"""")
```sql
INSERT INTO aluno (nomedoaluno, datadenascimento, primeiranota, segundanota,curso_id) VALUES
(
    'Cleitinho da Silva',
    '2000/05/25',
    10.00,
    8.00,
    2
),
(
    'Clara Amorim',
    '2007/04/15',
    6.00,
    7.00,
    1
),
(
    'João Ribeiro',
    '2002/10/19',
    8.00,
    4.00,
    3
),
(
    'Nathalya Ordones',
    '2001/04/19',
    2.00,
    5.00,
    4
),
(
    'Alana Rocha',
    '2005/02/13',
    10.00,
    9.00,
    5
),
(
    'Ana Luísa Simões',
    '2003/11/29',
    7.00,
    6.00,
    2
),
(
    'Manuela Rodrigues',
    '2002/02/02',
    7.50,
    8.00,
    5
),
(
    'Caio Almeida',
    '2001/09/22',
    5.00,
    2.00,
    1
),
(
    'Sofia Holanda',
    '2004/06/09',
    5.00,
    6.00,
    3
),
(
    'Alicia Alves',
    '2007/08/17',
    10.00,
    10.00,
    4
);
```

```sql
-- faznedo ligação de curso para professor
ALTER TABLE curso 
ADD CONSTRAINT fk_curso_professor 
FOREIGN KEY (professor_id) REFERENCES professor(id);

-- fazendo ligação de aluno ao curso
ALTER TABLE aluno 
ADD CONSTRAINT fk_aluno_curso 
FOREIGN KEY (curso_id) REFERENCES curso(id);
```

