
Twig est le moteur de template par défaut dans Symfony, offrant une syntaxe concise et expressive pour générer des vues. Comprendre Twig est crucial pour créer des interfaces utilisateur dynamiques et interactives.

### Variables et Affichage

Dans Twig, les variables peuvent être définies et affichées simplement. Par exemple, pour afficher une variable dans une vue, utilisez la syntaxe `{{ variable }}`. 

```twig
{# Définir une variable #}
{% set nom_utilisateur = 'John' %}

{# Afficher la variable #}
{{ 'Bienvenue, ' ~ nom_utilisateur ~ '!' }}
```

Dans cet exemple, la variable `nom_utilisateur` est définie avec la valeur 'John', puis affichée dans la vue.

### Structures de Contrôle

Twig offre des structures de contrôle familières, telles que les boucles `for` et les conditions `if`.

```twig
{% for i in 1..5 %}
    {{ i }}
{% endfor %}

{% if condition %}
    {# Code à exécuter si la condition est vraie #}
{% else %}
    {# Code à exécuter si la condition est fausse #}
{% endif %}
```

### Inclusion de Fragments

Pour rendre vos vues modulaires, vous pouvez inclure des fragments de code avec `{% include 'chemin/vers/fragment.html.twig' %}`.

```twig
{# Dans le fichier parent.html.twig #}
{% include 'header.html.twig' %}

{# Dans le fichier header.html.twig #}
<header>
    <h1>Mon Site Web</h1>
</header>
```

### Boucles et Tableaux Associatifs

Twig facilite la manipulation des tableaux et des boucles. Par exemple, pour parcourir un tableau associatif :

```twig
{% for key, value in tableau_associatif %}
    {{ key }}: {{ value }}
{% endfor %}
```

### Filtres Twig

Les filtres Twig permettent de manipuler et de formater les données. Par exemple, pour convertir du texte en majuscules, utilisez le filtre `upper` :

```twig
{{ texte | upper }}
```

### Conditions et Boucles Avancées

Twig offre également des fonctionnalités avancées pour les conditions et les boucles, telles que `else if` et `loop`.

```twig
{% if condition %}
    {# Code à exécuter si la condition est vraie #}
{% elseif autre_condition %}
    {# Code à exécuter si une autre condition est vraie #}
{% else %}
    {# Code à exécuter si aucune des conditions n'est vraie #}
{% endif %}

{% for item in tableau %}
    {{ loop.index }}: {{ item }}
{% endfor %}
```

### Intégration avec les Contrôleurs Symfony

Dans vos contrôleurs Symfony, vous pouvez passer des variables à vos vues Twig pour les rendre dynamiques.

```php
// Dans un contrôleur Symfony
public function monAction(): Response
{
    $nom_utilisateur = 'John';
    
    return $this->render('ma_vue.html.twig', [
        'nom_utilisateur' => $nom_utilisateur,
    ]);
}
```

Dans la vue Twig associée (`ma_vue.html.twig`), vous pouvez maintenant accéder à la variable `$nom_utilisateur` comme mentionné précédemment.

En maîtrisant ces concepts de base de Twig, vous serez en mesure de créer des vues flexibles et dynamiques pour vos applications Symfony. N'hésitez pas à explorer davantage la documentation Twig pour découvrir toutes ses fonctionnalités.