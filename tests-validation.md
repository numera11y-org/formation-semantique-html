# Tests et validation

## Outils de vérification de la sémantique HTML

Plusieurs outils permettent de vérifier la sémantique et la validité du code HTML :

- Le validateur HTML du W3C est l'outil de référence pour vérifier la conformité du code HTML aux standards. Il permet de détecter les erreurs de syntaxe et les problèmes de structure.
- Des extensions de navigateur comme HTML5 Outliner permettent de visualiser la structure sémantique d'une page directement dans le navigateur.
- Des outils en ligne comme Nu Html Checker offrent une analyse détaillée du code HTML avec des suggestions d'amélioration.

## Méthodes d'audit d'accessibilité

Pour auditer l'accessibilité d'un site web, on peut utiliser :

- Des outils automatisés comme WAVE ou aXe qui détectent de nombreux problèmes d'accessibilité.
- Des tests manuels avec des lecteurs d'écran et la navigation au clavier pour vérifier l'expérience réelle des utilisateurs.
- Des méthodes d'audit RGAA qui permettent d'évaluer la conformité aux normes d'accessibilité de manière exhaustive.
- Des tests avec des utilisateurs en situation de handicap pour identifier les problèmes concrets d'utilisation.

## Correction des erreurs courantes

Voici quelques erreurs fréquentes à corriger :

- Absence de textes alternatifs pour les images.
- Structure de titres incorrecte ou incohérente.
- Contrastes de couleurs insuffisants.
- Formulaires mal étiquetés ou sans instructions claires.
- Contenus non accessibles au clavier.
- Absence de landmarks ARIA pour structurer la page.

Pour corriger ces erreurs, il faut :

- Revoir systématiquement le code HTML et les feuilles de style.
- Utiliser les outils de vérification automatisés pour détecter les problèmes.
- Former les équipes aux bonnes pratiques d'accessibilité.
- Mettre en place des processus de contrôle qualité avant mise en ligne.

Voici quelques exercices et corrigés pour le chapitre sur les techniques avancées d'accessibilité :

## Exercice 1 : Utilisation des attributs ARIA

Améliorez l'accessibilité du menu de navigation suivant en utilisant les attributs ARIA appropriés :

```html
<nav>
  <ul>
    <li><a href="#accueil">Accueil</a></li>
    <li><a href="#produits">Produits</a>
      <ul>
        <li><a href="#nouveautes">Nouveautés</a></li>
        <li><a href="#meilleures-ventes">Meilleures ventes</a></li>
      </ul>
    </li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>
```

Corrigé :

```html
<nav aria-label="Menu principal">
  <ul role="menubar">
    <li role="none"><a href="#accueil" role="menuitem">Accueil</a></li>
    <li role="none">
      <a href="#produits" role="menuitem" aria-haspopup="true" aria-expanded="false">Produits</a>
      <ul role="menu" aria-label="Sous-menu Produits">
        <li role="none"><a href="#nouveautes" role="menuitem">Nouveautés</a></li>
        <li role="none"><a href="#meilleures-ventes" role="menuitem">Meilleures ventes</a></li>
      </ul>
    </li>
    <li role="none"><a href="#contact" role="menuitem">Contact</a></li>
  </ul>
</nav>
```

## Exercice 2 : Gestion du focus

Écrivez une fonction JavaScript pour gérer le focus lors de l'ouverture et de la fermeture d'une boîte de dialogue modale.

Corrigé :

```javascript
let lastFocus;
const modal = document.getElementById('maModale');
const firstFocusableElement = modal.querySelector('button, [href], input, select, textarea, [tabindex]:not([tabindex="-1"])');

function ouvrirModale() {
  lastFocus = document.activeElement;
  modal.style.display = 'block';
  firstFocusableElement.focus();
  modal.addEventListener('keydown', gererFocusModale);
}

function fermerModale() {
  modal.style.display = 'none';
  modal.removeEventListener('keydown', gererFocusModale);
  lastFocus.focus();
}

function gererFocusModale(e) {
  const focusableElements = modal.querySelectorAll('button, [href], input, select, textarea, [tabindex]:not([tabindex="-1"])');
  const firstElement = focusableElements[0];
  const lastElement = focusableElements[focusableElements.length - 1];

  if (e.key === 'Tab') {
    if (e.shiftKey) {
      if (document.activeElement === firstElement) {
        lastElement.focus();
        e.preventDefault();
      }
    } else {
      if (document.activeElement === lastElement) {
        firstElement.focus();
        e.preventDefault();
      }
    }
  }
}
```