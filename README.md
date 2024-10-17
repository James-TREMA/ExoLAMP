```markdown
# Déploiement d'une stack LAMP avec Docker Compose

Ce projet met en place une stack LAMP (Linux, Apache, MySQL, PHP) avec Docker Compose. Il comprend un serveur web Apache avec PHP, une base de données MySQL, ainsi qu'Adminer, une interface web pour gérer la base de données.

## Contenu du projet

- **docker-compose.yml** : Ce fichier configure les différents services :
  - Un serveur Apache avec PHP (version 7.4).
  - Une base de données MySQL (version 5.7) avec un volume pour la persistance des données.
  - Adminer, un outil web pour gérer la base de données MySQL.
  
- **app/index.php** : Fichier PHP simple qui affiche les informations PHP à l'aide de la fonction `phpinfo()`.

- **Images** : 
  - `img/Image DB.png` : Capture d'écran de la base de données prouvant que le service est fonctionnel.
  - `img/Info PHP.png` : Capture d'écran de l'interface PHP affichant les informations sur PHP.

## Prérequis

- [Docker](https://www.docker.com/) et [Docker Compose](https://docs.docker.com/compose/install/) doivent être installés sur votre machine.

## Installation

1. Clonez ce dépôt sur votre machine locale :
   ```bash
   git clone https://github.com/James-TREMA/ExoLAMP.git
   cd ExoLAMP
   ```

2. Lancez Docker Compose pour démarrer les services :
   ```bash
   docker-compose up -d
   ```

3. Accédez aux services :
   - Le serveur web Apache avec PHP est disponible sur `http://localhost`.
   - Adminer est accessible sur `http://localhost:8080`.

4. Pour vérifier la configuration PHP, ouvrez votre navigateur et allez sur :
   ```bash
   http://localhost
   ```

5. Pour gérer la base de données, connectez-vous à Adminer à l'adresse :
   ```bash
   http://localhost:8080
   ```
   Utilisez les identifiants suivants :
   - **Système** : MySQL
   - **Serveur** : `db`
   - **Utilisateur** : `root`
   - **Mot de passe** : `example`
   - **Base de données** : `mydb`

## Persistance des données

Les données de la base de données sont persistées dans un volume Docker nommé `db_data`. Ce volume est monté sur le dossier `/var/lib/mysql` du conteneur MySQL.

## Commandes utiles

- Pour arrêter les services :
  ```bash
  docker-compose down
  ```

- Pour afficher les logs des services :
  ```bash
  docker-compose logs
  ```

## Captures d'écran

- **Image DB.png** : Confirmation que la base de données fonctionne correctement.
- **Info PHP.png** : Confirmation que l'environnement PHP est correctement configuré.

## Auteur

Projet réalisé par **James-TREMA**.

```

Pour ajouter ce fichier dans ton dépôt, tu peux créer un fichier nommé `README.md` à la racine du projet avec le contenu ci-dessus, puis l'ajouter à Git et le pousser sur GitHub :

```bash
git add README.md
git commit -m "Ajout du fichier README"
git push
```