# Instruções
Implemente e trate uma conexão com o seu banco de dados, usando JavaScript. Caso a conexão com o banco tenha sucesso, ele deve retornar uma frase positiva. Se isso não ocorrer, retorne uma frase informando o erro.

## CÓDIGO EM JS

```JS
const mysql = require('mysql');

const dbConfig = {
    host: 'localhost', 
    user: 'jedson', 
    password: 'jedson', 
    database: 'test',
    port: 3306
  };


const connection = mysql.createConnection(dbConfig);

connection.connect((err) => {
  if (err) {
    console.error('Erro ao conectar ao banco de dados:', err);
  } else {
    console.log('Conexão bem-sucedida com o banco de dados.');
  }
});

```
