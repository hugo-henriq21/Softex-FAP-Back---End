# Instruções
Produtos
Colunas: ProdutoID (Chave Primária), Nome do Produto, Preço, Quantidade em Estoque.
Crie os seguintes comandos para inserção e manipulação de dados, partindo do pressuposto de que os de criação da tabela já foram criados. Eles são:
1. inserção de produtos (INSERT): insira três novos produtos na tabela "Produtos" com os seguintes dados:
- produto 1: Nome - "Smartphone", Preço - 799.99, Quantidade - 20 unidades em estoque;
- produto 2: Nome - "Tablet", Preço - 349.99, Quantidade - 10 unidades em estoque;
- produto 3: Nome - "Fone de Ouvido", Preço - 49.99, Quantidade - 50 unidades em estoque.
2. atualização de estoque (UPDATE): atualize o estoque do "Smartphone" para 25 unidades e o preço para 849.99 na tabela "Produtos."
3. venda de produtos (DELETE): simule a venda de cinco unidades do "Tablet" e dez unidades do "Fone de Ouvido." Atualize o estoque na tabela "Produtos de acordo com as vendas.

## Código MySql:

``` JS
INSERT INTO Produtos (NomeProduto, Preco, QuantidadeEmEstoque)
VALUES
    ('Smartphone', 799.99, 20),
    ('Tablet', 349.99, 10),
    ('Fone de Ouvido', 49.99, 50);

// Atualização de estoque e preço para o "Smartphone"
UPDATE Produtos
SET QuantidadeEmEstoque = 25, Preco = 849.99
WHERE NomeProduto = 'Smartphone';

// Simulação de venda de cinco unidades do "Tablet"
UPDATE Produtos
SET QuantidadeEmEstoque = QuantidadeEmEstoque - 5
WHERE NomeProduto = 'Tablet';

// Simulação de venda de dez unidades do "Fone de Ouvido"
UPDATE Produtos
SET QuantidadeEmEstoque = QuantidadeEmEstoque - 10
WHERE NomeProduto = 'Fone de Ouvido';

```
