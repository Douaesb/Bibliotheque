# Système de Gestion de Bibliothèque Municipale

Cette application Java console permet de gérer efficacement l'inventaire des livres et magazines dans une bibliothèque municipale, ainsi que les emprunts et retours. Le projet est développé en Java 8, en suivant une architecture en couches pour séparer les responsabilités.

## Table des Matières

- [Installation](#installation)
- [Utilisation](#utilisation)
- [Architecture du Projet](#architecture-du-projet)
- [Fonctionnalités](#fonctionnalités)
- [Contributions](#contributions)
- [License](#license)

## Installation

### Prérequis

Avant de commencer, assurez-vous d'avoir les éléments suivants installés sur votre machine :

- [Java 8 ou supérieur](https://www.oracle.com/java/technologies/javase-jdk8-downloads.html)
- [Maven](https://maven.apache.org/) (optionnel, pour la gestion des dépendances)

### Étapes d'installation

1. Clonez le dépôt de l'application sur votre machine locale :

    ```bash
    git clone https://github.com/Douaesb/Bibliotheque.git
    cd système-gestion-bibliotheque
    ```

2. Compilez le projet avec Maven (optionnel) :

    ```bash
    mvn clean install
    ```

3. Si vous n'utilisez pas Maven, compilez les fichiers Java manuellement :

    ```bash
    javac -d bin src/**/*.java (linux)
    javac -d bin (Get-ChildItem -Path src -Recurse -Filter *.java).FullName (windows)
    ```

4. Lancez l'application depuis la classe `Main` :

    ```bash
   java -cp bin Main
    ```

### Exécution de l'application

   Vous pouvez exécuter l'application directement en utilisant Java Jar :

- 
    ```bash
    java -jar bin/bibliotheque.jar
    ```
## Utilisation
### Menu Interactif

L'application présente un menu interactif dans la console avec les options suivantes :

1. **Ajouter un document** (livre ou magazine)
2. **Emprunter un document**
3. **Retourner un document**
4. **Afficher tous les documents**
5. **Rechercher un document**
6. **Quitter l'application**

### Validation des Entrées

- Le système vérifie les entrées utilisateur pour éviter les erreurs (par exemple, dates au mauvais format ou choix invalide dans le menu).

### Exemple d'Utilisation

Une fois l'application lancée, vous pouvez interagir avec le menu en entrant le numéro correspondant à l'option souhaitée.

## Architecture du Projet

### Couche de Présentation

- **ConsoleUI** : Gère l'interface utilisateur et les interactions avec la console.

### Couche Métier

- **Document** (abstraite) : Définit les attributs et méthodes de base pour les documents (id, titre, auteur, date de publication, etc.).
- **Livre** : Hérite de `Document`, ajoute l'attribut ISBN, et implémente les méthodes abstraites.
- **Magazine** : Hérite de `Document`, ajoute l'attribut numéro, et implémente les méthodes abstraites.
- **Bibliotheque** : Gère la collection de documents à l'aide de `ArrayList` et `HashMap`.

### Couche Utilitaire

- **DateUtils** : Fournit des méthodes pour manipuler les dates (parsing et formatage) en utilisant Java Time API.

## Fonctionnalités

1. **Ajouter un document** : Ajoutez des livres ou des magazines à la bibliothèque avec un ID généré automatiquement.
2. **Emprunter un document** : Marquez un document comme emprunté s'il est disponible.
3. **Retourner un document** : Marquez un document comme retourné.
4. **Afficher tous les documents** : Liste tous les documents de la bibliothèque.
5. **Rechercher un document** : Recherchez un document par son titre.

## Contributions

Les contributions sont les bienvenues. Pour contribuer :

1. Forkez le projet.
2. Créez une branche pour votre fonctionnalité (`git checkout -b feature/NouvelleFonctionnalite`).
3. Commitez vos modifications (`git commit -am 'Ajout d'une nouvelle fonctionnalité'`).
4. Poussez votre branche (`git push origin feature/NouvelleFonctionnalite`).
5. Ouvrez une Pull Request.

## License

Ce projet est sous licence MIT. Voir le fichier [LICENSE](LICENSE) pour plus de détails.
