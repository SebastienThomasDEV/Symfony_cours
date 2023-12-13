
Maintenant que nous avons évoqué brièvement la structure du projet Symfony, approfondissons chaque composant avec des exemples concrets.

### Répertoire `src`

Le répertoire `src` est le cœur de votre application. Il contient le code source de votre application Symfony. Les fichiers PHP dans ce répertoire correspondent généralement aux différentes fonctionnalités de votre application.

**Exemple :** Création d'un contrôleur dans `src/Controller`.

```php
// src/Controller/DefaultController.php

namespace App\Controller;

use Symfony\Component\HttpFoundation\Response;
use Symfony\Component\Routing\Annotation\Route;

class HomePageController
{
    #[Route("/", name="app_homepage")]
    public function index(): Response
    {
        return $this->render('default/index.html.twig', [
            'message' => 'je suis un controller'
        ])
    }
}
```

Dans cet exemple, nous avons créé un contrôleur avec une action `index` associée à la route `/`. Le nom de la route est `app_homepage`.

### Répertoire `config`

Le répertoire `config` contient la configuration de votre application Symfony. Le fichier `config/routes.yaml` déclare les routes de votre application.

**Exemple :** Déclaration de routes dans `config/routes.yaml`.

```yaml
# config/routes.yaml
app_homepage:
    path: /
    controller: App\Controller\DefaultController::index
```

Dans cet exemple, nous déclarons une route avec le chemin `/` associé à la méthode `index` du contrôleur `DefaultController`.

### Répertoire `templates`

Symfony utilise le moteur de template Twig pour générer des pages HTML. Les fichiers Twig sont stockés dans le répertoire `templates`.

**Exemple :** Création d'un fichier Twig dans `templates/default/index.html.twig`.

```html
{# templates/default/index.html.twig #}

<!DOCTYPE html>
<html>
    <head>
        <title>Ma Page d'Accueil</title>
    </head>
    <body>
        <h1>{{ message }}</h1>
    </body>
</html>
```

Ce fichier Twig est associé à l'action `index` du contrôleur `DefaultController`. Il génère la page d'accueil avec le message de bienvenue.

### Répertoire `public`

Le répertoire `public` contient les fichiers publics de votre application, tels que les images, les feuilles de style et les scripts JavaScript. Ces fichiers peuvent être accédés directement par les utilisateurs.

**Exemple :** Ajout d'une image dans `public/images/logo.png`.

Vous pouvez accéder à cette image via l'URL : `http://localhost:8000/images/logo.png`.

Ces exemples illustrent la structure de base d'une application Symfony et comment les différents répertoires interagissent pour créer des pages web dynamiques. Explorez davantage la documentation de Symfony pour découvrir d'autres fonctionnalités et optimisations offertes par la version 6 du framework. Bon développement !