# README - Insertion de Données Aléatoires
### Outils : 
- https://sqlflow.gudusoft.com/#/
- https://livesql.oracle.com/apex/f?p=590:1000
## Introduction

Ce document décrit les étapes pour insérer des données aléatoires dans les tables `EMP`, `DEPT`, `PROJET`, et `PARTICIPATION` dans une base de données Oracle. Ces tables ont été créées avec les contraintes d'intégrité nécessaires pour gérer les employés, les départements, les projets et les participations des employés aux projets.

## Création des Tables

Voici les commandes SQL pour créer les tables nécessaires avec les contraintes d'intégrité:

```sql
CLEAR SCREEN;

-- Table des employés
CREATE TABLE EMP(
    Matricule   VARCHAR2(3),
    NomE        VARCHAR2(15),
    Poste       VARCHAR2(10),
    DatEmb      DATE,
    Salaire     INTEGER,
    Commission  NUMBER(26,2),
    NumDept     NUMBER(26) 
);

-- Table des départements
CREATE TABLE DEPT (
    NumDept INTEGER,
    NomDept VARCHAR2(15),
    Lieu VARCHAR2(10)
);

-- Table des projets
CREATE TABLE PROJET(
    CodeP   NUMBER(26),
    NomP    VARCHAR2(15),
    DateP   DATE
);

-- Table des participations
CREATE TABLE PARTICIPATION(
    Matricule   VARCHAR2(3),
    CodeP       NUMBER(26),
    Fonction    VARCHAR2(10)
);
```

## Insertion de Données Aléatoires

### Table `EMP`

```sql
INSERT INTO EMP (Matricule, NomE, Poste, DatEmb, Salaire, Commission, NumDept) VALUES ('E01', 'Dupont', 'Manager', TO_DATE('2020-01-15', 'YYYY-MM-DD'), 50000, 5000.50, 1);
INSERT INTO EMP (Matricule, NomE, Poste, DatEmb, Salaire, Commission, NumDept) VALUES ('E02', 'Durand', 'Analyste', TO_DATE('2021-05-22', 'YYYY-MM-DD'), 45000, 3000.00, 2);
INSERT INTO EMP (Matricule, NomE, Poste, DatEmb, Salaire, Commission, NumDept) VALUES ('E03', 'Martin', 'Développeur', TO_DATE('2019-09-10', 'YYYY-MM-DD'), 40000, 2500.75, 3);
INSERT INTO EMP (Matricule, NomE, Poste, DatEmb, Salaire, Commission, NumDept) VALUES ('E04', 'Bernard', 'Testeur', TO_DATE('2022-11-05', 'YYYY-MM-DD'), 35000, 2000.00, 1);
```

### Table `DEPT`

```sql
INSERT INTO DEPT (NumDept, NomDept, Lieu) VALUES (1, 'Informatique', 'Paris');
INSERT INTO DEPT (NumDept, NomDept, Lieu) VALUES (2, 'Ressources Humaines', 'Lyon');
INSERT INTO DEPT (NumDept, NomDept, Lieu) VALUES (3, 'Finance', 'Marseille');
INSERT INTO DEPT (NumDept, NomDept, Lieu) VALUES (4, 'Marketing', 'Bordeaux');
```

### Table `PROJET`

```sql
INSERT INTO PROJET (CodeP, NomP, DateP) VALUES (101, 'Projet Alpha', TO_DATE('2023-01-01', 'YYYY-MM-DD'));
INSERT INTO PROJET (CodeP, NomP, DateP) VALUES (102, 'Projet Beta', TO_DATE('2023-06-15', 'YYYY-MM-DD'));
INSERT INTO PROJET (CodeP, NomP, DateP) VALUES (103, 'Projet Gamma', TO_DATE('2024-02-20', 'YYYY-MM-DD'));
INSERT INTO PROJET (CodeP, NomP, DateP) VALUES (104, 'Projet Delta', TO_DATE('2023-12-05', 'YYYY-MM-DD'));
```

### Table `PARTICIPATION`

```sql
INSERT INTO PARTICIPATION (Matricule, CodeP, Fonction) VALUES ('E01', 101, 'Chef de projet');
INSERT INTO PARTICIPATION (Matricule, CodeP, Fonction) VALUES ('E02', 102, 'Analyste');
INSERT INTO PARTICIPATION (Matricule, CodeP, Fonction) VALUES ('E03', 103, 'Développeur');
INSERT INTO PARTICIPATION (Matricule, CodeP, Fonction) VALUES ('E04', 104, 'Testeur');
```

## Requêtes de Sélection

Pour vérifier les données insérées, vous pouvez utiliser les commandes `SELECT` suivantes :

```sql
SELECT * FROM EMP;
SELECT * FROM DEPT;
SELECT * FROM PROJET;
SELECT * FROM PARTICIPATION;
```

## Exemples d'Insertions Incorrectes

### Exemple 1 : Dépassement de la taille `VARCHAR2`

```sql
-- NomE dépasse la taille maximale de 15 caractères
INSERT INTO EMP (Matricule, NomE, Poste, DatEmb, Salaire, Commission, NumDept) VALUES ('E05', 'DupontDupontDupont', 'Manager', TO_DATE('2020-01-15', 'YYYY-MM-DD'), 50000, 5000.50, 1);
```

**Erreur attendue** : `ORA-12899: valeur trop grande pour la colonne "EMP"."NomE" (réelle: 18, maximale: 15)`

### Exemple 2 : Clé étrangère non existante

```sql
-- NumDept ne correspond à aucun département existant
INSERT INTO EMP (Matricule, NomE, Poste, DatEmb, Salaire, Commission, NumDept) VALUES ('E06', 'Lemoine', 'Manager', TO_DATE('2020-01-15', 'YYYY-MM-DD'), 50000, 5000.50, 10);
```

**Erreur attendue** : `ORA-02291: violation de contrainte d'intégrité (nom_de_contrainte) - clé mère non trouvée`

### Exemple 3 : Valeur numérique hors des limites

```sql
-- Commission dépasse la taille maximale définie
INSERT INTO EMP (Matricule, NomE, Poste, DatEmb, Salaire, Commission, NumDept) VALUES ('E07', 'Petit', 'Analyste', TO_DATE('2021-05-22', 'YYYY-MM-DD'), 45000, 12345678901234567890123456.78, 2);
```

**Erreur attendue** : `ORA-01438: valeur plus grande que la précision spécifiée autorisée pour cette colonne`

