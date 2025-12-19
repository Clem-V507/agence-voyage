# agence-voyage

Projet de développement du SI d’une agence de voyage

---

## Exercice 1 : Modélisation du SI d’une agence de voyage 

### Étape 0 : Création du projet

Pour bien commencer le projet, nous avons créé un GitHub Repository [``agence-voyage``](https://github.com/Clem-V507/agence-voyage) accompagné d'un GitHub Project [``Suivi des tâches``](https://github.com/users/Clem-V507/projects/2), sous forme de tableau Kanban, pour le suivi de l'avancement du projet.

### Étape 1 : Préparation du dictionnaire de données

À partir des règles de gestion prédéfinies, nous avons pu construire un tableau Excel ([``Dictionnaire_donnees.xlsx``](Dictionnaire_donnees.xlsx)), appelé dictionnnaire de donnée, référençant les attributs, primary key (PK) et foreign key (FK) par entité, leur type de données et description, associés à ces règles.

### Étape 2 : Épurer un dictionnaire de données

Après analyse du dictionnaire de données, nous avons constater que celui-ci ne nécessitait pas d'être épuré. Aucune mise-à-jour du fichier n'a donc été effectué.

### Étape 3 : Graphe des dépendances fonctionnelles

#### Travail 1 : Contraintes et règles d’intégrité principales
- Chaque entité se doit d’avoir une primary key (PK).
- Les entités utilisant un ou des attributs d’autres entités, se doivent d’avoir une ou plusieurs foreign key (FK).
- Selon les règles de gestion définies plus haut, certains attributs se doivent d’avoir des valeurs uniques.

#### Travail 2 : Dépendances fonctionnelles (DF)
Tout d'abord, nous avons identifié les dépendances fonctionnnelles par entité : 
- ``Client`` : id_client → nom_client, prenom_client, adresse_client, ca
- ``Accompagnateur`` : id_accompagnateur → nom_accompagnateur, prenom_accompagnateur, adresse_accompagnateur
- ``Pays`` : id_pays → nom_pays
- ``Ville`` : id_ville → nom_ville, id_pays
- ``Hotel`` : id_hotel → nom_hotel, adresse_hotel, id_ville
- ``Circuit`` : id_circuit → intitule_circuit, date_depart, date_arrivee, date_limite_1, date_limite_2, id_ville_depart, id_ville_arrivee, id_hotel, transport, id_accompagnateur, nb_places, prix
- ``Réservation`` : id_reservation → id_client, id_circuit, date_demande, nb_places_reservees, acompte, solde, remise, remboursement, statut
<br>Puis, pour avoir une vision plus globale, nous nous sommes concentrés sur les dépendances inter-entité : 
- Globales : id_reservation → id_client, id_circuit → id_accompagnateur, id_hotel → id_ville → id_pays

#### Travail 3 : Graphe des dépendances fonctionnelles (GDF)
Après avoir effectué l'étape précédente, nous avons pu construire les graphes des dépendances fonctionnelles sur le même schéma.
<br>Premièrement, un graphe par entité :
- ``Client`` : [Schéma Canva](https://www.canva.com/design/DAG7kt2YIwg/K7bTKc5UGsLLWAFE7NpT0g/edit?utm_content=DAG7kt2YIwg&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)
- ``Accompagnateur`` : [Schéma Canva](https://www.canva.com/design/DAG7km34YAI/Sa4rz6ttsP4htLGQ_ltzVQ/edit?utm_content=DAG7km34YAI&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)
- ``Pays`` : [Schéma Canva](https://www.canva.com/design/DAG7koP9nio/rIXU4UiBDT2koLnzqUg8jQ/edit?utm_content=DAG7koP9nio&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)
- ``Ville`` : [Schéma Canva](https://www.canva.com/design/DAG7koBUknc/7CeAhiZZTYPyEkxn9fhS6A/edit?utm_content=DAG7koBUknc&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)
- ``Hotel`` : [Schéma Canva](https://www.canva.com/design/DAG7kroOWn8/QL_4dsjzrLjCbk1cOG0Efw/edit?utm_content=DAG7kroOWn8&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)
- ``Circuit`` : [Schéma Canva](https://www.canva.com/design/DAG7kuRfHOs/5ROXuQdjdOqW8F4LwvZakA/edit?utm_content=DAG7kuRfHOs&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)
- ``Réservation`` : [Schéma Canva](https://www.canva.com/design/DAG7krwkqHU/L_6k1_hC1al4NOPTYAQHZg/edit?utm_content=DAG7krwkqHU&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)
<br>Deuxièmement, un graphe inter-entité :
- Globale : [Schéma Canva](https://www.canva.com/design/DAG7SSVKi0o/rHj_6YPSpbUhJglYqP4O4g/edit?utm_content=DAG7SSVKi0o&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton)

### Étape 4 : Schéma du modèle conceptuel de données (MCD)

Au cours de cette étape, nous avons construit, en suivant les actions demandées, le modèle conceptuel de données (MCD), que vous trouverez au format png dans ce Repository, ainsi que sous forme de [Schéma Canva](https://www.canva.com/design/DAG7mI6Jxy8/DX6Ywl3JSXKL2O-Fj0m5xw/edit?utm_content=DAG7mI6Jxy8&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton).
