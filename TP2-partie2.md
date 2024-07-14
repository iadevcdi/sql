# README : Opérations sur la Base de Données avec la Table CUSTOMERS

Ce README fournit un guide sur la création, l'insertion, la mise à jour, la suppression et la sélection de données dans une table `CUSTOMERS` à l'aide de commandes SQL. Il inclut également des instructions pour créer, renommer et manipuler des tables.

## Table des Matières

1. [Suppression de Table](#suppression-de-table)
2. [Création de Table](#création-de-table)
3. [Insertion de Données](#insertion-de-données)
4. [Sélection de Données](#sélection-de-données)
5. [Mise à Jour de Données](#mise-à-jour-de-données)
6. [Suppression de Données](#suppression-de-données)
7. [Description de la Table](#description-de-la-table)
8. [Création de Nouvelles Tables](#création-de-nouvelles-tables)
9. [Gestion des Contraintes](#gestion-des-contraintes)
10. [Renommage de Table](#renommage-de-table)

## Suppression de Table

Pour supprimer une table existante de la base de données :

```sql
DROP TABLE CUSTOMERS;
```

**Challenge :** Que se passe-t-il si vous essayez de supprimer une table qui n'existe pas ?

## Création de Table

Pour créer la table `CUSTOMERS` :

```sql
CREATE TABLE CUSTOMERS (
    ID INT NOT NULL,
    NAME VARCHAR (20) NOT NULL,
    AGE INT NOT NULL,
    ADDRESS CHAR (25),
    SALARY DECIMAL (18, 2),
    PRIMARY KEY (ID)
);
```

**Challenge :** Créez une table similaire nommée `EMPLOYEES` avec des colonnes supplémentaires pour le `DEPARTMENT` et le `HIRE_DATE`.

## Insertion de Données

Pour insérer des données dans la table `CUSTOMERS` :

```sql
INSERT INTO CUSTOMERS (ID, NAME, AGE, ADDRESS, SALARY)
VALUES (1, 'John', 32, 'New York', 2000.00);

INSERT INTO CUSTOMERS (ID, NAME, AGE, ADDRESS, SALARY)
VALUES (2, 'Sarah', 25, 'Los Angeles', 1500.00);

INSERT INTO CUSTOMERS (ID, NAME, AGE, ADDRESS, SALARY)
VALUES (3, 'Michael', 23, 'Chicago', 2000.00);

INSERT INTO CUSTOMERS (ID, NAME, AGE, ADDRESS, SALARY)
VALUES (4, 'Emma', 25, 'Houston', 6500.00);

INSERT INTO CUSTOMERS (ID, NAME, AGE, ADDRESS, SALARY)
VALUES (5, 'Daniel', 27, 'Phoenix', 8500.00);

INSERT INTO CUSTOMERS (ID, NAME, AGE, ADDRESS, SALARY)
VALUES (6, 'Sophia', 22, 'Philadelphia', 4500.00);

INSERT INTO CUSTOMERS (ID, NAME, AGE, ADDRESS, SALARY)
VALUES (7, 'James', 30, 'San Antonio', 3000.00);

INSERT INTO CUSTOMERS (ID, NAME, AGE, ADDRESS, SALARY)
VALUES (8, 'Olivia', 28, 'San Diego', 5500.00);
```

**Challenge :** Insérez un nouveau client nommé `Robert`, âgé de 35 ans, vivant à `Dallas` avec un salaire de `4000.00`.

## Sélection de Données

Pour récupérer toutes les données de la table `CUSTOMERS` :

```sql
SELECT * FROM CUSTOMERS;
```

**Challenge :** Sélectionnez uniquement les clients ayant un salaire supérieur à `3000.00`.

## Mise à Jour de Données

Pour mettre à jour les données dans la table `CUSTOMERS` :

```sql
UPDATE CUSTOMERS
SET SALARY = 5000.00
WHERE ID = 2;
```

**Challenge :** Modifiez l'adresse du client avec l'ID `4` pour qu'elle soit `Miami`.

## Suppression de Données

Pour supprimer des données de la table `CUSTOMERS` :

```sql
DELETE FROM CUSTOMERS
WHERE ID = 3;
```

**Challenge :** Supprimez tous les clients dont l'âge est inférieur à `25`.

## Description de la Table

Pour décrire la structure de la table `CUSTOMERS` :

```sql
DESCRIBE CUSTOMERS;
```

**Challenge :** Décrivez la structure de la table `EMPLOYEES` que vous avez créée dans le challenge précédent.

## Création de Nouvelles Tables

Pour créer de nouvelles tables à partir de la table `CUSTOMERS` :

```sql
CREATE TABLE CLIENT1 AS SELECT * FROM CUSTOMERS;
CREATE TABLE CLIENT2 AS SELECT * FROM CUSTOMERS WHERE 1=0;
```

Pour sélectionner des données des nouvelles tables :

```sql
SELECT * FROM CLIENT1;
SELECT * FROM CLIENT2;
```

**Challenge :** Créez une nouvelle table `CLIENT3` à partir de `CUSTOMERS` en ne sélectionnant que les clients ayant un salaire supérieur à `5000.00`.

## Gestion des Contraintes

Pour gérer les contraintes sur la table `CUSTOMERS` :

Lister les contraintes :
```sql
SELECT constraint_name, constraint_type, status 
FROM USER_CONSTRAINTS 
WHERE UPPER(table_name) = 'CUSTOMERS';
```

Désactiver une contrainte :
```sql
ALTER TABLE CUSTOMERS DISABLE CONSTRAINT <NOM_CONTRAINTE>;
```

Activer une contrainte :
```sql
ALTER TABLE CUSTOMERS ENABLE CONSTRAINT <NOM_CONTRAINTE>;
```

**Challenge :** Désactivez puis réactivez la contrainte de clé primaire sur la table `CUSTOMERS`.

## Renommage de Table

Pour renommer une table :

```sql
RENAME CLIENT2 TO CLI2;
```

Pour sélectionner des données de la table renommée :

```sql
SELECT * FROM CLI2;
```

**Challenge :** Renommez la table `CLIENT1` en `CLIENT_A`.

Ce README fournit les opérations de base pour gérer et manipuler des tables et des données dans une base de données SQL. Chaque section se termine par un challenge pour renforcer votre compréhension et vos compétences en SQL.
