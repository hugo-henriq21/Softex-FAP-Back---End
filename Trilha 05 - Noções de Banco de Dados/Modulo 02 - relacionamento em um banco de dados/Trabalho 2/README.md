# Instruções:

Tarefas:
1. Crie um banco de dados chamado "BlogDB.";
2. Crie as tabelas a seguir.
a) "Post" - Colunas: PostID (Chave Primária), Título, Conteúdo, Data de Publicação, AutorID (Chave Estrangeira para a tabela Autor). b) "Autor" - Colunas: AutorID (Chave Primária), Nome do Autor, E-mail.
c) "Comentario" - Colunas: ComentariolD (Chave Primária), Texto do Comentário, Data do Comentário, AutorID (Chave Estrangeira para a tabela Autor), PostID (Chave Estrangeira para a tabela Post).
3. Defina a integridade referencial entre as tabelas, de acordo com as relações descritas (um post é escrito por um autor, um autor pode escrever vários posts, um post pode ter vários comentários, um comentário é escrito por um autor).

