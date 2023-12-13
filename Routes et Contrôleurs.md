
## Les Routes 

Les routes définissent comment les URL de votre application sont associées à des actions spécifiques, généralement représentées par des contrôleurs.
Dans Symfony , la définition des routes peut être réalisée à l'aide de l'attribut
`#[Route()]`.

Voici un exemple simple pour illustrer cela :

```php
// src/Controller/DefaultController.php

namespace App\Controller;

use Symfony\Component\HttpFoundation\Response;
use Symfony\Component\Routing\Annotation\Route;

class DefaultController
{
    #[Route("/", name: "home")]
    public function index(): Response
    {
        return new Response("Bienvenue sur la page d'accueil !");
    }

    #[Route("/article/{id}", name: "article_detail"]
    public function showArticle(Article $article): Response
    {
        // Logique pour afficher un article en fonction de l'ID
        return new Response($article);
    }
}
```

Dans cet exemple, la classe `DefaultController` possède deux actions (`index` et `showArticle`). L'attribut `#[Route()]` est utilisé pour définir les URL associées à ces actions. La route "/" est associée à la méthode `index`, et la route "/article/{id}" est associée à la méthode `showArticle`, prenant un paramètre d'URL `id`.

>[!info]
>Dans cette exemple la méthode `showArticle` prend en paramètre une entité Article, Symfony va automatiquement essayer de retrouver l'entité en fonction de l'id que vous avez passerez en paramètre dans votre URL.
> Exemple: `/article/2`.
>Il ira chercher l'entité Article avec l'id deux dans votre base de données.

## Contrôleurs Symfony

Les contrôleurs dans Symfony sont des classes responsables de traiter les requêtes HTTP (les requêtes vers le serveur) et de renvoyer une réponse. Voici un exemple de contrôleur :

```php
// src/Controller/ProductController.php

namespace App\Controller;

use Symfony\Bundle\FrameworkBundle\Controller\AbstractController;
use Symfony\Component\HttpFoundation\Response;
use Symfony\Component\Routing\Annotation\Route;

class ProductController extends AbstractController
{
    #[Route("/product", name: "product_create")]
    public function show(): Response
    {
        // Logique pour créer un product
        $product = new Product();
        $product->setPrice(20);

        return $this->render('product/detail.html.twig', [
            'product' => $product,
        ]);
    }
}
```


