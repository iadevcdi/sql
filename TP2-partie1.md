# SELECT

- https://www.w3schools.com/sql/sql_select.asp


### Script SQL

```sql
-- Create the customers table
CREATE TABLE customers (
    CustomerID INT,
    CustomerName VARCHAR(255),
    ContactName VARCHAR(255),
    Address VARCHAR(255),
    City VARCHAR(255),
    PostalCode VARCHAR(50),
    Country VARCHAR(50)
);

-- Insert records into the customers table
INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (1, 'Alfreds Futterkiste', 'Maria Anders', 'Obere Str. 57', 'Berlin', '12209', 'Germany');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (2, 'Ana Trujillo Emparedados y helados', 'Ana Trujillo', 'Avda. de la Constitución 2222', 'México D.F.', '05021', 'Mexico');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (3, 'Antonio Moreno Taquería', 'Antonio Moreno', 'Mataderos 2312', 'México D.F.', '05023', 'Mexico');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (4, 'Around the Horn', 'Thomas Hardy', '120 Hanover Sq.', 'London', 'WA1 1DP', 'UK');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (5, 'Berglunds snabbköp', 'Christina Berglund', 'Berguvsvägen 8', 'Luleå', 'S-958 22', 'Sweden');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (6, 'Blauer See Delikatessen', 'Hanna Moos', 'Forsterstr. 57', 'Mannheim', '68306', 'Germany');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (7, 'Blondel père et fils', 'Frédérique Citeaux', '24, place Kléber', 'Strasbourg', '67000', 'France');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (8, 'Bólido Comidas preparadas', 'Martín Sommer', 'C/ Araquil, 67', 'Madrid', '28023', 'Spain');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (9, 'Bon app''', 'Laurence Lebihan', '12, rue des Bouchers', 'Marseille', '13008', 'France');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (10, 'Eastern Connection', 'Ann Devon', '35 King George', 'London', 'WX3 6FW', 'UK');

-- Insert additional records into the customers table
INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (11, 'Frankenversand', 'Peter Franken', 'Berliner Platz 43', 'München', '80805', 'Germany');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (12, 'France restauration', 'Carine Schmitt', '54, rue Royale', 'Nantes', '44000', 'France');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (13, 'Franchi S.p.A.', 'Paolo Accorti', 'Via Monte Bianco 34', 'Torino', '10100', 'Italy');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (14, 'Furia Bacalhau e Frutos do Mar', 'Lino Rodriguez', 'Jardim das rosas n. 32', 'Lisboa', '1675', 'Portugal');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (15, 'Galería del gastrónomo', 'Eduardo Saavedra', 'Rambla de Cataluña, 23', 'Barcelona', '08022', 'Spain');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (16, 'Godos Cocina Típica', 'José Pedro Saavedra', 'C/ Romero, 33', 'Sevilla', '41101', 'Spain');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (17, 'Gourmet Lanchonetes', 'André Fonseca', 'Av. Brasil, 442', 'Campinas', '04876-786', 'Brazil');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (18, 'Great Lakes Food Market', 'Howard Snyder', '2732 Baker Blvd.', 'Eugene', '97403', 'USA');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (19, 'Großhandel Ottowitz', 'Renate Messner', 'Sierras de Granada 9993', 'Buenos Aires', '1053', 'Argentina');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (20, 'Hanari Carnes', 'Mario Pontes', 'Rua do Paço, 67', 'Rio de Janeiro', '05454-876', 'Brazil');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (21, 'Alfreds Futterkiste', 'Maria Anders', 'Obere Str. 57', 'Berlin', '12209', 'Germany');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (22, 'Ana Trujillo Emparedados y helados', 'Ana Trujillo', 'Avda. de la Constitución 2222', 'México D.F.', '05021', 'Mexico');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (23, 'Antonio Moreno Taquería', 'Antonio Moreno', 'Mataderos 2312', 'México D.F.', '05023', 'Mexico');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (24, 'Around the Horn', 'Thomas Hardy', '120 Hanover Sq.', 'London', 'WA1 1DP', 'UK');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (25, 'Berglunds snabbköp', 'Christina Berglund', 'Berguvsvägen 8', 'Luleå', 'S-958 22', 'Sweden');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (26, 'Blauer See Delikatessen', 'Hanna Moos', 'Forsterstr. 57', 'Mannheim', '68306', 'Germany');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (27, 'Blondel père et fils', 'Frédérique Citeaux', '24, place Kléber', 'Strasbourg', '67000', 'France');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (28, 'Bólido Comidas preparadas', 'Martín Sommer', 'C/ Araquil, 67', 'Madrid', '28023', 'Spain');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (29, 'Bon app', 'Laurence Lebihan', '12, rue des Bouchers', 'Marseille', '13008', 'France');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (30, 'Eastern Connection', 'Ann Devon', '35 King George', 'London', 'WX3 6FW', 'UK');

INSERT INTO customers (CustomerID, CustomerName, ContactName, Address, City, PostalCode, Country)
VALUES (31, 'Frankenversand', 'Peter Franken', 'Berliner Platz 43', 'München', '80805', 'Germany');

```



### Exercice 1: Sélection de données de base
1. Sélectionnez tous les champs de la table.
    ```sql
    SELECT * FROM customers;
    ```

2. Sélectionnez uniquement les champs `CustomerName` et `City` de tous les enregistrements.
    ```sql
    SELECT CustomerName, City FROM customers;
    ```

### Exercice 2: Filtration des données
1. Sélectionnez tous les enregistrements où le pays est 'Mexico'.
    ```sql
    SELECT * FROM customers WHERE Country = 'Mexico';
    ```

2. Sélectionnez les enregistrements où la ville est 'London' et affichez uniquement les champs `CustomerName` et `Address`.
    ```sql
    SELECT CustomerName, Address FROM customers WHERE City = 'London';
    ```

### Exercice 3: Tri des données
1. Sélectionnez tous les enregistrements et triez-les par `CustomerName` en ordre alphabétique.
    ```sql
    SELECT * FROM customers ORDER BY CustomerName;
    ```

2. Sélectionnez tous les enregistrements et triez-les par `Country`, puis par `City`.
    ```sql
    SELECT * FROM customers ORDER BY Country, City;
    ```

### Exercice 4: Agrégation des données
1. Comptez le nombre total de clients.
    ```sql
    SELECT COUNT(*) FROM customers;
    ```

2. Comptez le nombre de clients dans chaque pays.
    ```sql
    SELECT Country, COUNT(*) FROM customers GROUP BY Country;
    ```

### Exercice 5: Utilisation des fonctions d'agrégation
1. Trouvez le nom du client et la ville des enregistrements où le code postal commence par '05'.
    ```sql
    SELECT CustomerName, City FROM customers WHERE PostalCode LIKE '05%';
    ```

2. Sélectionnez le nombre total de clients dans chaque ville et affichez uniquement les villes ayant plus de 1 client.
    ```sql
    SELECT City, COUNT(*) as NumberOfCustomers 
    FROM customers 
    GROUP BY City 
    HAVING COUNT(*) > 1;
    ```

### Exercice 6: Mise à jour et suppression des données
1. Mettez à jour le nom du contact pour le client dont le `CustomerID` est 1 à 'Marie Andersson'.
    ```sql
    UPDATE customers 
    SET ContactName = 'Marie Andersson' 
    WHERE CustomerID = 1;
    ```

2. Supprimez les enregistrements où le pays est 'Germany'.
    ```sql
    DELETE FROM customers WHERE Country = 'Germany';
    ```






