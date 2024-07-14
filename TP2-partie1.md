# SELECT

- https://www.w3schools.com/sql/sql_select.asp


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






