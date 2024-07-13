# Exercices Pratiques - Manipulation de Données SQL

## Exercices d'Insertion

### Table `EMP`

1. **Insertion d'un nouvel employé :**
```sql
INSERT INTO EMP (Matricule, NomE, Poste, DatEmb, Salaire, Commission, NumDept) VALUES ('E06', 'Garcia', 'Analyste', TO_DATE('2023-07-20', 'YYYY-MM-DD'), 38000, 2000.00, 2);
```

2. **Insertion d'un employé avec commission nulle :**
```sql
INSERT INTO EMP (Matricule, NomE, Poste, DatEmb, Salaire, Commission, NumDept) VALUES ('E07', 'Petit', 'Manager', TO_DATE('2022-12-15', 'YYYY-MM-DD'), 52000, 0, 1);
```

3. **Insertion d'un nouvel employé sans commission :**
```sql
INSERT INTO EMP (Matricule, NomE, Poste, DatEmb, Salaire, Commission, NumDept) VALUES ('E08', 'Lefevre', 'Développeur', TO_DATE('2023-01-05', 'YYYY-MM-DD'), 42000, NULL, 3);
```

4. **Insertion d'un employé dans un nouveau département :**
```sql
INSERT INTO EMP (Matricule, NomE, Poste, DatEmb, Salaire, Commission, NumDept) VALUES ('E09', 'Lemoine', 'Chef de projet', TO_DATE('2023-08-10', 'YYYY-MM-DD'), 48000, 3000.50, 4);
```

5. **Insertion d'un employé avec une date d'embauche récente :**
```sql
INSERT INTO EMP (Matricule, NomE, Poste, DatEmb, Salaire, Commission, NumDept) VALUES ('E10', 'Roux', 'Testeur', TO_DATE('2024-06-01', 'YYYY-MM-DD'), 40000, 1500.75, 1);
```

### Table `DEPT`

1. **Insertion d'un nouveau département :**
```sql
INSERT INTO DEPT (NumDept, NomDept, Lieu) VALUES (6, 'Support', 'Nantes');
```

2. **Insertion d'un département supplémentaire :**
```sql
INSERT INTO DEPT (NumDept, NomDept, Lieu) VALUES (7, 'Logistique', 'Nice');
```

3. **Insertion d'un département dans une nouvelle localisation :**
```sql
INSERT INTO DEPT (NumDept, NomDept, Lieu) VALUES (8, 'Service Client', 'Strasbourg');
```

4. **Insertion d'un département avec un numéro existant :**
```sql
INSERT INTO DEPT (NumDept, NomDept, Lieu) VALUES (5, 'Maintenance', 'Lyon');
```

5. **Insertion d'un département avec un nom de département existant :**
```sql
INSERT INTO DEPT (NumDept, NomDept, Lieu) VALUES (9, 'Informatique', 'Toulouse');
```

### Table `PROJET`

1. **Insertion d'un nouveau projet :**
```sql
INSERT INTO PROJET (CodeP, NomP, DateP) VALUES (105, 'Projet Zeta', TO_DATE('2024-08-15', 'YYYY-MM-DD'));
```

2. **Insertion d'un projet avec une date future :**
```sql
INSERT INTO PROJET (CodeP, NomP, DateP) VALUES (106, 'Projet Eta', TO_DATE('2024-12-01', 'YYYY-MM-DD'));
```

3. **Insertion d'un projet avec une date proche :**
```sql
INSERT INTO PROJET (CodeP, NomP, DateP) VALUES (107, 'Projet Theta', TO_DATE('2024-07-31', 'YYYY-MM-DD'));
```

4. **Insertion d'un projet avec un nom de projet existant :**
```sql
INSERT INTO PROJET (CodeP, NomP, DateP) VALUES (108, 'Projet Alpha', TO_DATE('2024-09-10', 'YYYY-MM-DD'));
```

5. **Insertion d'un projet avec un code de projet existant :**
```sql
INSERT INTO PROJET (CodeP, NomP, DateP) VALUES (101, 'Projet Kappa', TO_DATE('2024-11-20', 'YYYY-MM-DD'));
```

### Table `PARTICIPATION`

1. **Insertion d'une nouvelle participation :**
```sql
INSERT INTO PARTICIPATION (Matricule, CodeP, Fonction) VALUES ('E06', 105, 'Analyste');
```

2. **Insertion d'une participation supplémentaire :**
```sql
INSERT INTO PARTICIPATION (Matricule, CodeP, Fonction) VALUES ('E07', 106, 'Développeur');
```

3. **Insertion d'une participation avec une fonction spécifique :**
```sql
INSERT INTO PARTICIPATION (Matricule, CodeP, Fonction) VALUES ('E08', 107, 'Chef de projet');
```

4. **Insertion d'une participation avec un matricule existant :**
```sql
INSERT INTO PARTICIPATION (Matricule, CodeP, Fonction) VALUES ('E01', 108, 'Testeur');
```

5. **Insertion d'une participation avec un code de projet existant :**
```sql
INSERT INTO PARTICIPATION (Matricule, CodeP, Fonction) VALUES ('E09', 101, 'Analyste');
```

## Exercices de Modification

1. **Modifier le salaire de l'employé 'Dupont' à 55000 :**
```sql
UPDATE EMP SET Salaire = 55000 WHERE NomE = 'Dupont';
```

2. **Modifier la fonction de l'employé 'Durand' à 'Manager' :**
```sql
UPDATE EMP SET Poste = 'Manager' WHERE NomE = 'Durand';
```

3. **Modifier le lieu du département 'Informatique' à 'Lille' :**
```sql
UPDATE DEPT SET Lieu = 'Lille' WHERE NomDept = 'Informatique';
```

4. **Modifier la date du projet 'Projet Beta' à '2023-07-01' :**
```sql
UPDATE PROJET SET DateP = TO_DATE('2023-07-01', 'YYYY-MM-DD') WHERE NomP = 'Projet Beta';
```

5. **Modifier la fonction de l'employé 'Martin' à 'Architecte' :**
```sql
UPDATE PARTICIPATION SET Fonction = 'Architecte' WHERE Matricule = 'E03' AND CodeP = 103;
```

## Exercices de Suppression

1. **Supprimer l'employé 'Bernard' :**
```sql
DELETE FROM EMP WHERE NomE = 'Bernard';
```

2. **Supprimer le département 'Marketing' :**
```sql
DELETE FROM DEPT WHERE NomDept = 'Marketing';
```

3. **Supprimer le projet 'Projet Delta' :**
```sql
DELETE FROM PROJET WHERE NomP = 'Projet Delta';
```

4. **Supprimer la participation de l'employé 'Dupont' au projet 'Projet Alpha' :**
```sql
DELETE FROM PARTICIPATION WHERE Matricule = 'E01' AND CodeP = 101;
```

5. **Supprimer tous les employés du département 'Finance' :**
```sql
DELETE FROM EMP WHERE NumDept = 3;
```

6. **Supprimer toutes les participations dans le projet 'Projet Epsilon' :**
```sql
DELETE FROM PARTICIPATION WHERE CodeP = 105;
```
