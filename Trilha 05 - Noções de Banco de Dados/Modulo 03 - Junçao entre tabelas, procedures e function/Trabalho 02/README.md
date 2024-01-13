# Instruções:

Considere um banco de dados simples que armazena informações sobre livros e autores. As tabelas relevantes são as seguintes: 1. Tabela "Autores":
Colunas: AutorID (Chave Primária), Nome, Nacionalidade
2. Tabela "Livros":
Colunas: LivroID (Chave Primária), Titulo, AnoPublicacao, AutorID (Chave Estrangeira referenciando Autores)
Instruções:
1. Inserção de dados: insira alguns registros nas tabelas "Autores" e "Livros". Certifique-se de que existam, pelo menos, três autores e cinco livros associados a esses autores;
2. Consulta simples: realize uma consulta simples para listar todos os autores e seus livros associados;
3. Consulta com junção INNER JOIN: crie uma consulta que utilize INNER JOIN para listar os detalhes dos livros e seus autores correspondentes;
4. Consulta com junção LEFT JOIN: elabore uma consulta que utilize LEFT JOIN para exibir todos os autores, independentemente de terem livros associados. Inclua informações dos livros, se disponíveis;
5. Consulta com filtro por nacionalidade: realize uma consulta que liste os autores e seus livros, mas restrinja os resultados apenas aos autores de uma nacionalidade específica;
6. Consulta agregada: crie uma consulta que agregue dados para contar quantos livros cada autor escreveu.  ﻿

# Código em SQL:

## Inserção de dados:

``` JS
-- Inserção de autores
INSERT INTO Autores (Nome, Nacionalidade) VALUES
('Autor1', 'Nacionalidade1'),
('Autor2', 'Nacionalidade2'),
('Autor3', 'Nacionalidade3');

-- Inserção de livros associados aos autores
INSERT INTO Livros (Titulo, AnoPublicacao, AutorID) VALUES
('Livro1', 2020, 1),
('Livro2', 2018, 1),
('Livro3', 2019, 2),
('Livro4', 2021, 2),
('Livro5', 2022, 3);

```

## Consulta simples:
``` JS
-- Inserção de autores
-- Consulta simples para listar autores e seus livros
SELECT Autores.Nome, Livros.Titulo
FROM Autores
JOIN Livros ON Autores.AutorID = Livros.AutorID;
```
Esta consulta lista todos os autores e seus livros associados.

## Consulta com INNER JOIN:
``` JS
-- Consulta utilizando INNER JOIN para listar detalhes de livros e seus autores
SELECT Autores.Nome, Livros.Titulo, Livros.AnoPublicacao
FROM Autores
JOIN Livros ON Autores.AutorID = Livros.AutorID;

```
Esta consulta retorna detalhes dos livros e seus autores correspondentes usando INNER JOIN.

## Consulta com LEFT JOIN:
``` JS
-- Consulta utilizando LEFT JOIN para exibir todos os autores, independentemente de terem livros associados
SELECT Autores.Nome, Livros.Titulo, Livros.AnoPublicacao
FROM Autores
LEFT JOIN Livros ON Autores.AutorID = Livros.AutorID;

```
Esta consulta retorna todos os autores, incluindo aqueles que não têm livros associados, e informações dos livros se disponíveis.

## Consulta com filtro por nacionalidade:
``` JS
-- Consulta que lista autores e seus livros, restringindo os resultados a uma nacionalidade específica
SELECT Autores.Nome, Livros.Titulo
FROM Autores
JOIN Livros ON Autores.AutorID = Livros.AutorID
WHERE Autores.Nacionalidade = 'Nacionalidade1';

```
Esta consulta lista autores e seus livros, mas apenas para autores de uma nacionalidade específica.

## Consulta agregada:

```JS
-- Consulta que conta quantos livros cada autor escreveu
SELECT Autores.Nome, COUNT(Livros.LivroID) AS QuantidadeLivros
FROM Autores
LEFT JOIN Livros ON Autores.AutorID = Livros.AutorID
GROUP BY Autores.Nome;

```
Esta consulta retorna o número de livros que cada autor escreveu, utilizando a função de agregação COUNT.



