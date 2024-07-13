# README - Manipulation de Données SQL

## Introduction

Ce document explique comment manipuler les données dans les tables `EMP`, `DEPT`, `PROJET`, et `PARTICIPATION` dans une base de données Oracle. Vous apprendrez à effectuer des insertions de données aléatoires, des sélections, des suppressions et des mises à jour dans ces tables.

## Utilisation des Outils

Pour les exercices décrits ici, vous pouvez utiliser les outils suivants :
- [SQLFlow](https://sqlflow.gudusoft.com/#/)
- [LiveSQL Oracle](https://livesql.oracle.com/apex/f?p=590:1000)

## Insertion de Données Aléatoires

Voici comment insérer des données aléatoires dans chaque table spécifiée :

### Table `EMP`

```sql
-- Exemple d'insertion pour un nouvel employé
INSERT INTO EMP (Matricule, NomE, Poste, DatEmb, Salaire, Commission, NumDept) VALUES ('E05', 'Lefevre', 'Développeur', TO_DATE('2023-03-10', 'YYYY-MM-DD'), 42000, 1500.25, 3);
```

### Table `DEPT`

```sql
-- Exemple d'insertion pour un nouveau département
INSERT INTO DEPT (NumDept, NomDept, Lieu) VALUES (5, 'Logistique', 'Toulouse');
```

### Table `PROJET`

```sql
-- Exemple d'insertion pour un nouveau projet
INSERT INTO PROJET (CodeP, NomP, DateP) VALUES (105, 'Projet Epsilon', TO_DATE('2024-07-01', 'YYYY-MM-DD'));
```

### Table `PARTICIPATION`

```sql
-- Exemple d'insertion pour une nouvelle participation
INSERT INTO PARTICIPATION (Matricule, CodeP, Fonction) VALUES ('E05', 105, 'Développeur');
```

## Requêtes de Sélection

Pour récupérer des données de chaque table, utilisez les commandes `SELECT` suivantes :

```sql
SELECT * FROM EMP;
SELECT * FROM DEPT;
SELECT * FROM PROJET;
SELECT * FROM PARTICIPATION;
```

## Exemples de Suppressions

### Supprimer un Employé

```sql
-- Supprimer un employé basé sur son matricule
DELETE FROM EMP WHERE Matricule = 'E05';
```

### Supprimer un Projet

```sql
-- Supprimer un projet basé sur son code
DELETE FROM PROJET WHERE CodeP = 105;
```

## Mises à Jour de Données

### Mettre à Jour le Salaire d'un Employé

```sql
-- Mettre à jour le salaire d'un employé
UPDATE EMP SET Salaire = 43000 WHERE Matricule = 'E04';
```
