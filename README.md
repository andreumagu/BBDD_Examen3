# EXAMEN SQL

1. Escribe una sentencia SQL que muestre el valor de todos los atributos de todos los registros de la tabla Customers.

    ```sql
    SELECT *
    FROM Customers;
    ```

    ![1](/img/1.png)

2. Escribe una sentencia SQL que muestre el valor máximo de todos los atributos de todos los registros de la tabla Customers.

    ```sql
    SELECT MAX(CustomerID), MAX(CustomerName), MAX(ContactName), MAX(Address), MAX(City), MAX(City), MAX(Country)
    FROM Customers;
    ```

    ![2](/img/2.png)

3. Escribe una sentencia SQL que muestre solo los valores de los atributos CustomerName y
City de todos los registros de la tabla Customers.

    ```sql
    SELECT CustomersName, City
    FROM Customers;
    ```

    ![3](/img/3.png)

4. Escribe una sentencia SQL para la tabla Customers que muestre todos los valores diferentes del atributo Country, sin mostrar duplicados.

    ```sql
    SELECT DISTINCT Country
    FROM Customers;
    ```

    ![4](/img/4.png)

5. Escribe una sentencia SQL que muestre los valores de todos los atributos de la tabla Customers, pero solo de los registros donde el atributo Country valga exactamente Mexico.

    ```sql
    SELECT *
    FROM Customers
    WHERE Country = 'Mexico';
    ```

    ![5](/img/5.png)

6. Escribe una sentencia SQL que muestre los valores de todos los atributos de la tabla Customers, pero solo de los registros donde el atributo Country valga Germany y simultáneamente el atributo City valga Berlin.

    ```sql
    SELECT *
    FROM Customers
    Where Country = 'Germany' AND City = 'Berlin';
    ```

    ![6](/img/6.png)

7. Escribe una sentencia SQL que muestre el nombre de todos los productos (ProductName) y el nombre de la categoría (CategorieName) a la que pertenece cada uno de los productos.
Las categorías se encuentran en la tabla Categories y los productos en la tabla Products.

    ```sql
    SELECT Products.ProductName, Category.CategoryName
    FROM Products
    INNER JOIN Category ON Products.CategoryID = Category.CategoryID;
    ```

    ![7](/img/7.png)

8. Escribe una sentencia SQL que muestre el nombre de todos los productos (ProductName) y el nombre de las categorías (CategorieName) a las que pertenecen cada uno de los productos así como también el nombre del proveedor (Suppliers). Las categorías se encuentran a la tabla Categories, los productos a la tabla Products y los proveedores a la tabla Suppliers.

    ```sql
    SELECT Products.ProductName, Category.CategoryName, Suppliers.SupplierName
    FROM Products
    INNER JOIN Category ON Products.CategoryID = Category.CategoryID
    INNER JOIN Suppliers ON Products.SupplierID = Suppliers.SupplierID;
    ```

    ![8](/img/8.png)

9. Escribe una sentencia SQL que cuente el número de productos (Productos) por categorías (Categorías). Se tienen que mostrar dos columnas, CategorieName y el contador. Solo tienen que aparecer las categorías con productos. Las categorías se encuentran a la tabla
Categorías, los productos en la tabla Products.

    ```sql
    SELECT Category.CategoryName, COUNT(Products.ProductID)
    FROM Category
    INNER JOIN Products ON Category.CategoryID = Products.CategoryID
    GROUP BY Category.CategoryName;
    ```

    ![9](/img/9.png)

10. Escribe una sentencia SQL que cuente el número de productos (Productos) por categorías (Categorías). Solamente nos interesa contar el productos que su nombre empieza por P.
Tienen que aparecer las categorías que no tienen productos. Las categorías se encuentran en
la tabla Categorías, los productos en la tabla Products.

    ```sql
    SELECT Category.CategoryName, COUNT(Products.ProductID)
    FROM Category
    RIGHT JOIN Products ON Category.CategoryID = Products.CategoryID
    WHERE Products.ProductName LIKE 'P%'
    GROUP BY Category.CategoryName;
    ```

    ![10](/img/10.png)
