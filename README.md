# 2026-seance-functions-part-001

# Exercices Python - Les fonctions et la validation des saisies

## Objectif du projet

Ce projet a pour objectif de découvrir et mettre en pratique la notion de **fonction en Python**.

Les exercices proposés permettent d'apprendre à :
- créer des fonctions avec des paramètres ;
- retourner une valeur avec l'instruction `return` ;
- découper un programme en plusieurs fonctions réutilisables ;
- contrôler et sécuriser les saisies utilisateur ;
- utiliser les boucles `while` pour gérer les erreurs de saisie.

---

# Exercice 1 - Vérifier un caractère numérique

## Objectif

Créer une fonction permettant de vérifier si un caractère correspond à un chiffre.

## Fonction demandée

```python
isNumber(value)
```
Description

La fonction reçoit un caractère en paramètre et retourne :

True si le caractère est compris entre '0' et '9' ;
False sinon.

## Exemple
```python
isNumber('5')
```
Résultat : True
```python
isNumber('A')
```
Résultat : False
### Contraintes
Ne pas utiliser les fonctions Python :
 - isdigit()
 - isnumeric()
   
# Exercice 2 - Lire un entier sécurisé

## Objectif

Créer une fonction permettant de lire un entier saisi par l'utilisateur.

Fonction demandée
```python
lireEntier(message)
```
##Description

### La fonction :

 - affiche un message à l'utilisateur ;
 - récupère une saisie clavier ;
 - vérifie que la valeur saisie correspond bien à un entier ;
 - redemande une saisie en cas d'erreur ;
 - retourne l'entier valide.
- Valeurs acceptées

| Saisie	| Résultat|
|---------|---------|
|25	      | Valide  |
|0	      | Valide  |
|-12	    | Valide  |
|12a	    |Invalide |
|3.5	    |Invalide |

## Contraintes

La fonction doit utiliser : isNumber() pour contrôler chaque caractère.

## Exercice 3 - Lire un entier dans un intervalle
### Objectif

Créer une fonction permettant de contrôler une valeur comprise entre deux bornes.

### Fonction demandée
```python
lireEntierMinMax(message, mini, maxi)
```
## Paramètres
### Paramètre	Description
 - message	Message affiché lors de la saisie
 - mini	    Valeur minimale autorisée
 - maxi	    Valeur maximale autorisée

### Description

La fonction doit :

 - demander un entier à l'utilisateur ;
 - vérifier que la saisie est correcte ;
 - vérifier que la valeur appartient à l'intervalle [mini ; maxi] ;
 - recommencer la saisie tant que la valeur est incorrecte ;
 - retourner la valeur valide.

# Exercice 4 – Mise en place d'une batterie de tests pour les fonctions de saisie
## Objectif

Mettre en place un programme de tests permettant de vérifier le bon fonctionnement des fonctions développées précédemment :

 - isNumber()
 - lireEntier()
 - lireEntierMinMax()

L'objectif est de s'assurer que les fonctions répondent correctement aux différents cas d'utilisation (valeurs correctes et erreurs de saisie).

## Contexte

Lors du développement d'un programme, il est nécessaire de vérifier que les fonctions réalisées fonctionnent correctement.

Pour cela, on va créer un fichier Python dédié aux tests permettant de contrôler automatiquement les résultats obtenus.

## Travail demandé

 - Créer un fichier : tests_fonctions.py
      Ce fichier devra importer les fonctions réalisées précédemment :
      from fonctions import isNumber, lireEntier, lireEntierMinMax

## Partie 1 – Tester la fonction isNumber()
### Objectif

Vérifier que la fonction reconnaît correctement les caractères numériques.

### Travail demandé

Créer une fonction de test :
```python
test_isNumber()
```
Cette fonction devra tester plusieurs situations :

## Batterie de tests `isNumber()`

| N° Test | Valeur testée | Résultat attendu | Résultat obtenu |
|---------|----------------|------------------|-----------------|
| 1 | `'0'` | `True` | |
| 2 | `'5'` | `True` | |
| 3 | `'9'` | `True` | |
| 4 | `'A'` | `False` | |
| 5 | `'x'` | `False` | |
| 6 | `'-'` | `False` | |
| 7 | `' '` | `False` | |

Pour chaque test, afficher :
  OK si le résultat obtenu correspond au résultat attendu ;
  ERREUR sinon.


## Partie 2 – Tester la fonction lireEntier()
### Objectif

Vérifier que la fonction permet de récupérer uniquement des nombres entiers valides.

### Travail demandé

Créer une fonction :
```python
test_lireEntier()
```
Effectuer plusieurs essais :

Test 1 : entier positif
=======================
Exemple :
---------

Saisie utilisateur : 25

Résultat attendu : 25

Test 2 : entier négatif
=======================
Exemple :
---------
Saisie utilisateur : -15

Résultat attendu : -15

Test 3 : saisie incorrecte
==========================
Tester des saisies invalides :

- abc
- 12.5
- 10a

La fonction doit demander une nouvelle saisie jusqu'à obtenir un entier valide.

## Partie 3 – Tester la fonction lireEntierMinMax()
### Objectif

Vérifier le contrôle d'un entier compris dans un intervalle.

### Travail demandé

Créer une fonction :
```python
test_lireEntierMinMax()
```
Réaliser les tests suivants :

Test d'une note scolaire

Intervalle :

0 <= note <= 20

Tester :

|Saisie	| Résultat |
--------------------
|-5	    | Refusée  |
|25    	| Refusée  |
|15	    | Acceptée |

Test d'un nombre d'élèves

Intervalle :

1 <= nombre <= 30

Tester :

|Saisie	|Résultat  |
-------------------
|   0  | Refusée  |
| 35	  | Refusée  |
| 20	  | Acceptée |


## Partie 4 – Programme principal de test

Créer un programme principal permettant d'exécuter l'ensemble des tests.

Structure attendue :
```python
if __name__ == "__main__":

    test_isNumber()

    test_lireEntier()

    test_lireEntierMinMax()
```
    
## Organisation du projet

Le projet devra avoir l'organisation suivante :
```text
FonctionsPython/
│
├── fonctions.py
│
├── tests_fonctions.py
│
└── README.md
```

## Contraintes
Ne pas modifier les fonctions à tester.
Les tests doivent être regroupés dans un fichier séparé.
Chaque test doit afficher clairement son résultat.
Le code doit être organisé avec des fonctions.
Utiliser des messages explicites pour faciliter l'analyse des erreurs.

###Exemple de résultat attendu
```python
===== TEST isNumber() =====

OK : '5' est un chiffre
OK : 'A' n'est pas un chiffre


===== TEST lireEntier() =====

Saisie correcte : 25


===== TEST lireEntierMinMax() =====

25 refusé (hors intervalle)
15 accepté


===== FIN DES TESTS =====
```

## Compétences évaluées
|Compétence	|Validation|
|-----------|----------|
|Importer une fonction depuis un module	|✅|
|Créer des fonctions de test	|✅|
|Vérifier un résultat attendu	|✅|
|Utiliser des conditions	|✅|
|Structurer un programme Python	|✅|
|Comprendre l'intérêt des tests	|✅|
