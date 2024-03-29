# INSTRUÇÔES
﻿

Você faz parte da equipe de análise de dados da TechData, uma empresa de tecnologia renomada. Ela coleta uma enorme quantidade de dados de seus produtos, usuários e transações. Recentemente, essa empresa decidiu aprimorar as suas habilidades de consulta de dados usando Data Query Language (DQL) para obter insights valiosos sobre o desempenho dos produtos, o comportamento do usuário e a eficácia das campanhas de marketing.
1. Seleção de dados: escreva uma consulta que selecione todos os dados de transações da tabela de transações;
2. Renomeando colunas: utilize a cláusula AS para renomear as colunas da consulta anterior para nomes mais descritivos, como ID_Transacao, Data, Valor etc.;
3. Filtragem com a cláusula WHERE: escreva uma consulta que selecione apenas as transações com um valor superior a R$ 100,00 4. Ordenação com a cláusula ORDER BY: ordene as transações por valor em ordem decrescente;
5. Agregação com funções SQL: utilize funções SQL como AVG, MAX, MIN e COUNT para calcular a média, o valor máximo, o valor mínimo e o número total de transações;
6. Agrupamento com a cláusula GROUP BY: agrupe as transações por produto e calcule a média de valor para cada produto; 7. Consulta combinada: escreva uma consulta que selecione a quantidade total de produtos vendidos (COUNT), o valor total das vendas (SUM) e a média de valor por transação, agrupados por categoria de produto.

# CÓDIGO SQL:
## SELEÇÃO DE DADOS:
``` JS
SELECT * FROM Transacoes;
   ```
## Renomeando colunas:
``` JS
SELECT ID_Transacao as ID, Data, Valor FROM Transacoes;
   ```
## Filtragem com a cláusula WHERE:
``` JS
SELECT * FROM Transacoes WHERE Valor > 100.00;

   ```
## Ordenação com a cláusula ORDER BY:
``` JS
SELECT * FROM Transacoes ORDER BY Valor DESC;
   ```
## Agregação com funções SQL:
``` JS

SELECT AVG(Valor) AS Media, MAX(Valor) AS ValorMaximo, MIN(Valor) AS ValorMinimo, COUNT(*) AS TotalTransacoes FROM Transacoes;

   ```
## Agrupamento com a cláusula GROUP BY:

``` JS

SELECT Produto, AVG(Valor) AS MediaValorPorProduto FROM Transacoes GROUP BY Produto;
   ```
## Consulta combinada:
``` JS
SELECT Categoria, COUNT(*) AS QuantidadeProdutos, SUM(Valor) AS ValorTotalVendas, AVG(Valor) AS MediaValorPorTransacao
FROM Produtos
GROUP BY Categoria;

   ```
