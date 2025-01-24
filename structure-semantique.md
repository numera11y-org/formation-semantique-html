# Structure sémantique des pages HTML

La structure sémantique des pages HTML est essentielle pour créer des sites web accessibles, bien organisés et faciles à comprendre pour les utilisateurs et les moteurs de recherche. Voici les points clés à retenir :

## Utilisation appropriée des balises de titre (h1-h6)

Les balises de titre permettent de structurer hiérarchiquement le contenu d'une page. Quelques règles importantes :

- Utilisez un seul `<h1>` par page, généralement pour le titre principal
- Respectez la hiérarchie des titres (h1 > h2 > h3, etc.) sans sauter de niveaux
- N'utilisez pas les balises de titre uniquement pour leur apparence visuelle

## Organisation du contenu avec les balises section, article, nav, etc.

Les balises sémantiques HTML5 permettent de donner du sens à la structure de la page :

- `<header>` : En-tête de la page ou d'une section
- `<nav>` : Navigation principale
- `<main>` : Contenu principal de la page
- `<article>` : Contenu autonome et indépendant
- `<section>` : Section thématique du contenu
- `<aside>` : Contenu connexe ou secondaire
- `<footer>` : Pied de page

## Création de points de repère ARIA (landmarks)

Les points de repère ARIA permettent d'améliorer la navigation pour les utilisateurs de technologies d'assistance :

- Utilisez les rôles ARIA appropriés (banner, navigation, main, complementary, etc.)
- Associez les rôles ARIA aux balises HTML5 correspondantes
- Assurez-vous que chaque zone importante de la page est identifiable

## Exercices et corrigés

### Exercice 1 : Structure sémantique

Transformez le code HTML suivant en utilisant une structure sémantique appropriée :

```html
<div class="header">
  <h1>Mon blog de voyage</h1>
  <div class="menu">
    <ul>
      <li><a href="#">Accueil</a></li>
      <li><a href="#">Destinations</a></li>
      <li><a href="#">À propos</a></li>
    </ul>
  </div>
</div>
<div class="content">
  <div class="post">
    <h2>Mon voyage à Paris</h2>
    <p>Contenu de l'article...</p>
  </div>
  <div class="sidebar">
    <h3>Articles récents</h3>
    <ul>
      <li><a href="#">Londres</a></li>
      <li><a href="#">Rome</a></li>
    </ul>
  </div>
</div>
<div class="footer">
  <p>&copy; 2025 Mon blog de voyage</p>
</div>
```

Corrigé :

```html
<header>
  <h1>Mon blog de voyage</h1>
  <nav>
    <ul>
      <li><a href="#">Accueil</a></li>
      <li><a href="#">Destinations</a></li>
      <li><a href="#">À propos</a></li>
    </ul>
  </nav>
</header>
<main>
  <article>
    <h2>Mon voyage à Paris</h2>
    <p>Contenu de l'article...</p>
  </article>
  <aside>
    <h3>Articles récents</h3>
    <ul>
      <li><a href="#">Londres</a></li>
      <li><a href="#">Rome</a></li>
    </ul>
  </aside>
</main>
<footer>
  <p>&copy; 2025 Mon blog de voyage</p>
</footer>
```

### Exercice 2 : Points de repère ARIA

Ajoutez les points de repère ARIA appropriés au code HTML suivant :

```html
<header>
  <h1>Site d'actualités</h1>
  <nav>
    <ul>
      <li><a href="#">Accueil</a></li>
      <li><a href="#">Politique</a></li>
      <li><a href="#">Économie</a></li>
    </ul>
  </nav>
</header>
<main>
  <h2>Dernières nouvelles</h2>
  <article>
    <h3>Titre de l'article</h3>
    <p>Contenu de l'article...</p>
  </article>
</main>
<aside>
  <h2>À la une</h2>
  <ul>
    <li><a href="#">Article populaire 1</a></li>
    <li><a href="#">Article populaire 2</a></li>
  </ul>
</aside>
<footer>
  <p>&copy; 2025 Site d'actualités</p>
</footer>
```

Corrigé :

```html
<header role="banner">
  <h1>Site d'actualités</h1>
  <nav role="navigation">
    <ul>
      <li><a href="#">Accueil</a></li>
      <li><a href="#">Politique</a></li>
      <li><a href="#">Économie</a></li>
    </ul>
  </nav>
</header>
<main role="main">
  <h2>Dernières nouvelles</h2>
  <article>
    <h3>Titre de l'article</h3>
    <p>Contenu de l'article...</p>
  </article>
</main>
<aside role="complementary">
  <h2>À la une</h2>
  <ul>
    <li><a href="#">Article populaire 1</a></li>
    <li><a href="#">Article populaire 2</a></li>
  </ul>
</aside>
<footer role="contentinfo">
  <p>&copy; 2025 Site d'actualités</p>
</footer>
```