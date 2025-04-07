# projeto-sql de vendas
# código sql para teste

CREATE TABLE produtos (
    ID_Produto INT AUTO_INCREMENT PRIMARY KEY,
    Nome_Produto VARCHAR(255),
    Marca_Produto VARCHAR(50),
    Preco_Unit DECIMAL(10,2),
    Custo_Unit DECIMAL(10,2)
);

INSERT INTO produtos (Nome_Produto, Marca_Produto, Preco_Unit, Custo_Unit)
VALUES 
    ('iPhone 14 Pro', 'Apple', 7000.00, 5000.00),
    ('MacBook Air M2', 'Apple', 12000.00, 9000.00),
    ('Redmi Note 12', 'Xiaomi', 2500.00, 1800.00),
    ('Xiaomi Pad 6', 'Xiaomi', 3000.00, 2200.00),
    ('Monitor LG 27"', 'LG', 1500.00, 1200.00);

SELECT 
    ID_Produto,
    Nome_Produto,
    Marca_Produto,
    Preco_Unit,
    Custo_Unit,
    CASE 
        WHEN Marca_Produto = 'Apple' THEN (1 - 0.15) * Custo_Unit
        WHEN Marca_Produto = 'Xiaomi' THEN (1 - 0.30) * Custo_Unit
        ELSE Custo_Unit
    END AS Valor_Com_Desconto
FROM produtos;
