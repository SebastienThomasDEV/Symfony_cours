# Cours sur la Prise en Main de Symfony 6

Bienvenue dans ce cours dédié à la prise en main du framework Symfony 6, un outil puissant pour le développement d'applications web robustes en PHP. Dans ce cours, nous allons couvrir les étapes d'installation de Symfony 6, ainsi que les premières notions essentielles pour comprendre le framework et démarrer votre propre application web.

## Installation de Symfony 6

Avant de commencer à travailler avec Symfony 6, vous devez vous assurer que votre environnement de développement est prêt. Symfony utilise Composer, un gestionnaire de dépendances pour PHP, pour simplifier le processus d'installation.

### Étapes d'installation

>[!important]
>**Composer & CLI Symfony :** Assurez vous que [Composer](https://getcomposer.org/) est installé sur votre système ainsi que la [CLI](https://symfony.com/download) Symfony.

Cette commande télécharge les dépendances nécessaires et configure un projet Symfony de base.

```
symfony new my_projet --webapp
```

>[!info]
>Vous pouvez spécifier votre version de symfony : 
>``symfony new my_projet --version="votreVersion"`` 
>Ainsi que pour le type d'application: 
>``symfony new my_projet --webapp``

*Ce rendre à l'aide de votre terminal dans le dossier du projet:*
```
cd my projet
```

*Puis lancez votre serveur de développement intégré de Symfony.*
```
symfony server:start
```

Vous pouvez accéder à votre application [ici.](http://localhost:8000).

>[!info]
>Vous pouvez démarrer votre serveur en mode détaché pour pouvoir exécuter des scripts dans la console.
>`symfony server:start -d`


Maintenant que Symfony est installé, plongeons nous dans les concepts clés du Framework.
## Notions Fondamentales de Symfony

### Structure du Projet

Symfony suit une structure de projet conventionnelle qui organise les fichiers de manière logique. Les répertoires importants incluent `src` (code source), `config` (configuration), `templates` (vues), et `public` (fichiers publics).

### Routes et Contrôleurs

Les routes définissent les URL de votre application et les associent à des contrôleurs. Un contrôleur gère la logique de traitement d'une requête et renvoie une réponse. Les routes sont configurées dans le fichier `config/routes.yaml`.

### Twig - Moteur de Template

Symfony utilise Twig comme moteur de template. Les fichiers Twig sont stockés dans le répertoire `templates` et permettent de générer dynamiquement du contenu HTML.

### Doctrine - Gestion de la Base de Données

Doctrine est intégré à Symfony pour la gestion de la base de données. Les entités définissent la structure de la base de données, et Doctrine facilite l'interaction avec celle-ci.

### Services et Injection de Dépendances

Symfony encourage l'utilisation de services pour découpler les composants de votre application. L'injection de dépendances permet de fournir les services nécessaires à d'autres parties de votre code.

### Console Symfony

La console Symfony est un outil puissant pour effectuer des tâches en ligne de commande telles que la création de contrôleurs, l'exécution de migrations, etc.