# Introduction à la sémantique HTML et à l'accessibilité web

## Définition et importance de la sémantique HTML

La sémantique HTML fait référence à l'utilisation des balises HTML pour donner un sens et une structure au contenu d'une page web, plutôt que simplement définir son apparence. L'utilisation correcte des éléments sémantiques permet aux navigateurs, moteurs de recherche et technologies d'assistance de mieux comprendre et interpréter le contenu.

L'importance de la sémantique HTML réside dans plusieurs aspects :

1. Accessibilité : Elle permet aux technologies d'assistance de mieux interpréter le contenu pour les utilisateurs ayant des besoins spécifiques.

2. SEO : Les moteurs de recherche utilisent la structure sémantique pour mieux comprendre et indexer le contenu.

3. Maintenabilité : Un code sémantique est plus facile à lire et à maintenir pour les développeurs.

4. Cohérence : Elle encourage une structure cohérente à travers les différentes pages d'un site.

Exemples d'éléments sémantiques HTML5 :

- `<header>` : En-tête de la page ou d'une section
- `<nav>` : Section de navigation
- `<main>` : Contenu principal de la page
- `<article>` : Contenu autonome et indépendant
- `<section>` : Section thématique du contenu
- `<aside>` : Contenu connexe ou secondaire
- `<footer>` : Pied de page

## Présentation des enjeux de l'accessibilité web

L'accessibilité web vise à rendre les sites et applications web utilisables par tous, y compris les personnes en situation de handicap. Les principaux enjeux sont :

1. Inclusion : Permettre à tous les utilisateurs d'accéder à l'information et aux services en ligne.

2. Légalité : De nombreux pays ont des lois exigeant l'accessibilité des sites web publics.

3. Élargissement de l'audience : Un site accessible peut atteindre un public plus large.

4. Amélioration de l'expérience utilisateur : Les pratiques d'accessibilité bénéficient souvent à tous les utilisateurs.

5. Optimisation pour les moteurs de recherche : De nombreuses pratiques d'accessibilité améliorent également le référencement.

## Introduction aux normes RGAA et WCAG

Le RGAA (Référentiel Général d'Amélioration de l'Accessibilité) est la norme française d'accessibilité web, tandis que les WCAG (Web Content Accessibility Guidelines) sont les directives internationales développées par le W3C.

Points clés :

- Le RGAA est basé sur les WCAG mais adapté au contexte français.
- Les deux normes définissent des critères de succès pour l'accessibilité.
- Elles sont organisées autour de principes fondamentaux : Perceptible, Utilisable, Compréhensible et Robuste.
- Les niveaux de conformité sont A (le plus bas), AA et AAA (le plus élevé).

## Exercices et corrigés

### Exercice 1 : Sémantique HTML

Convertissez la structure HTML suivante en utilisant des balises sémantiques appropriées :

```html
<div class="header">
  <h1>Mon site web</h1>
  <div class="nav">
    <ul>
      <li><a href="#">Accueil</a></li>
      <li><a href="#">À propos</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
  </div>
</div>
<div class="main">
  <div class="article">
    <h2>Article principal</h2>
    <p>Contenu de l'article...</p>
  </div>
  <div class="sidebar">
    <h3>Informations complémentaires</h3>
    <p>Contenu secondaire...</p>
  </div>
</div>
<div class="footer">
  <p>&copy; 2025 Mon site web</p>
</div>
```

Corrigé :

```html
<header>
  <h1>Mon site web</h1>
  <nav>
    <ul>
      <li><a href="#">Accueil</a></li>
      <li><a href="#">À propos</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
  </nav>
</header>
<main>
  <article>
    <h2>Article principal</h2>
    <p>Contenu de l'article...</p>
  </article>
  <aside>
    <h3>Informations complémentaires</h3>
    <p>Contenu secondaire...</p>
  </aside>
</main>
<footer>
  <p>&copy; 2025 Mon site web</p>
</footer>
```

### Exercice 2 : Accessibilité

Identifiez et corrigez les problèmes d'accessibilité dans le code HTML suivant :

```html
<img src="logo.png" />
<h1><font color="blue">Bienvenue sur notre site</font></h1>
<p onclick="window.location.href='page.html'">Cliquez ici pour plus d'informations</p>
<div style="background-color: yellow; color: white;">
  Information importante !
</div>
```

Corrigé :

```html
<img src="logo.png" alt="Logo de l'entreprise" />
<h1>Bienvenue sur notre site</h1>
<a href="page.html">Cliquez ici pour plus d'informations</a>
<div role="alert" style="background-color: yellow; color: black;">
  Information importante !
</div>
```

Explications des corrections :
- Ajout d'un attribut `alt` à l'image pour la décrire
- Suppression de la balise `<font>` obsolète, le style devrait être en CSS
- Remplacement du `<p>` avec `onclick` par un lien `<a>` plus accessible
- Ajout d'un rôle ARIA et amélioration du contraste pour le message important