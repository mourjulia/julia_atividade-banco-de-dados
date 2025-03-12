# Atividade de Bando de Dados - Etapa 4 (FINAL)

## 1- Faça uma consulta que mostre os alunos que nasceram antes do ano 2009

```sql
SELECT datadenascimento FROM aluno 
WHERE datadenascimento < '2009-01-01';
```

## 2- Faça uma consulta que calcule a média das notas de cada aluno e as mostre com duas casas decimais.

```sql
SELECT nomedoaluno, ROUND((primeiranota + segundanota) / 2, 2) AS "Média das notas" FROM aluno;
```

## 3- Faça uma consulta que calcule o limite de faltas de cada curso de acordo com a carga horária. Considere o limite como 25% da carga horária. Classifique em ordem crescente pelo título do curso.

```sql

```

## 4- Faça uma consulta que mostre os nomes dos professores que são somente da área "desenvolvimento".

```sql
SELECT nomedoprofessor FROM professor WHERE areadeatuacao = 'Desenvolvimento'
```
 ## 5- Faça uma consulta que mostre a quantidade de professores que cada área ("design", "infra", "desenvolvimento") possui.

 ```sql
 
 ```

## 6- Faça uma consulta que mostre o nome dos alunos, o título e a carga horária dos cursos que fazem.

```sql
SELECT 
    aluno.nomedoaluno AS Nome_Aluno, 
    curso.nomedocurso AS Curso, 
    curso.cargahoraria AS Carga_Horaria
FROM aluno
JOIN curso ON aluno.curso_id = curso.id
```

## 7- Faça uma consulta que mostre o nome dos professores e o título do curso que lecionam. Classifique pelo nome do professor.

```sql
SELECT 
    professor.nomedoprofessor AS Nome_Professor, 
    curso.nomedocurso AS Curso
FROM professor JOIN curso ON professor.curso_id = curso.id 
```

## 8- Faça uma consulta que mostre o nome dos alunos, o título dos cursos que fazem, e o professor de cada curso.

```sql
SELECT 
    aluno.nomedoaluno AS Nome_Aluno, 
    curso.nomedocurso AS Curso, 
    professor.nomedoprofessor AS Professor
FROM aluno INNER JOIN curso ON aluno.curso_id = curso.id
JOIN professor ON curso.professor_id = professor.id
```

## 9-  Faça uma consulta que mostre a quantidade de alunos que cada curso possui. Classifique os resultados em ordem descrecente de acordo com a quantidade de alunos.

```sql

```

## 10- Faça uma consulta que mostre o nome dos alunos, suas notas, médias, e o título dos cursos que fazem. Devem ser considerados somente os alunos de Front-End e Back-End. Mostre os resultados classificados pelo nome do aluno.

```sql

```

## 11- Faça uma consulta que altere o nome do curso de Figma para Adobe XD e sua carga horária de 10 para 15.

```sql
UPDATE curso SET nomedocurso = 'Adobe XD' WHERE id = 4
UPDATE curso SET cargahoraria = '15' WHERE id = 4
```

## 12- Faça uma consulta que exclua um aluno do curso de Redes de Computadores e um aluno do curso de UX/UI.

```sql

```

## 13- Faça uma consulta que mostre a lista de alunos atualizada e o título dos cursos que fazem, classificados pelo nome do aluno.

```sql

```