# Mise en pratique

## Exercice 1 : Refonte sémantique d'une page web existante

Prenons l'exemple d'une page d'accueil d'une entreprise de location de voitures nommée "AutoLoc". Voici le code HTML initial non sémantique :

```html
<div class="header">
  <img src="logo.png" alt="AutoLoc">
  <div class="menu">
    <a href="#">Accueil</a>
    <a href="#">Véhicules</a>
    <a href="#">Tarifs</a>
    <a href="#">Contact</a>
  </div>
</div>

<div class="main">
  <div class="titre">
    <h1>Bienvenue chez AutoLoc</h1>
  </div>
  
  <div class="content">
    <div class="promo">
      <h2>Offre spéciale</h2>
      <p>-20% sur les locations de plus de 7 jours !</p>
    </div>
    
    <div class="vehicules">
      <h2>Nos véhicules</h2>
      <div class="voiture">
        <img src="citadine.jpg" alt="">
        <p>Citadines</p>
      </div>
      <div class="voiture">
        <img src="berline.jpg" alt="">
        <p>Berlines</p>
      </div>
      <div class="voiture">
        <img src="suv.jpg" alt="">
        <p>SUV</p>
      </div>
    </div>
  </div>
</div>

<div class="footer">
  <p>&copy; 2025 AutoLoc - Tous droits réservés</p>
</div>
```

Votre tâche est de refondre cette page en utilisant des balises sémantiques appropriées, en améliorant l'accessibilité et en structurant correctement le contenu.

Corrigé :

```html
<header>
  <img src="logo.png" alt="Logo AutoLoc">
  <nav>
    <ul>
      <li><a href="#">Accueil</a></li>
      <li><a href="#">Véhicules</a></li>
      <li><a href="#">Tarifs</a></li>
      <li><a href="#">Contact</a></li>
    </ul>
  </nav>
</header>

<main>
  <h1>Bienvenue chez AutoLoc</h1>
  
  <section aria-labelledby="offre-speciale">
    <h2 id="offre-speciale">Offre spéciale</h2>
    <p>-20% sur les locations de plus de 7 jours !</p>
  </section>
  
  <section aria-labelledby="nos-vehicules">
    <h2 id="nos-vehicules">Nos véhicules</h2>
    <ul>
      <li>
        <img src="citadine.jpg" alt="Illustration d'une citadine">
        <p>Citadines</p>
      </li>
      <li>
        <img src="berline.jpg" alt="Illustration d'une berline">
        <p>Berlines</p>
      </li>
      <li>
        <img src="suv.jpg" alt="Illustration d'un SUV">
        <p>SUV</p>
      </li>
    </ul>
  </section>
</main>

<footer>
  <p>&copy; 2025 AutoLoc - Tous droits réservés</p>
</footer>
```

## Exercice 2 : Création d'un composant accessible - Champ de mot de passe

Créez un champ de mot de passe accessible avec les fonctionnalités suivantes :
- Indication de la force du mot de passe
- Bouton pour afficher/masquer le mot de passe
- Instructions sur les critères du mot de passe
- Gestion des erreurs

Voici un exemple de mise en œuvre :

```html
<div class="password-field">
  <label for="password">Mot de passe :</label>
  <div class="password-input-wrapper">
    <input type="password" id="password" name="password" required
           aria-describedby="password-requirements password-strength"
           pattern="(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{8,}"
           onInput="checkPasswordStrength(this.value)">
    <button type="button" class="toggle-password" aria-label="Afficher le mot de passe"
            onclick="togglePasswordVisibility()">
      <span class="show-password">👁️</span>
      <span class="hide-password" hidden>🔒</span>
    </button>
  </div>
  <div id="password-requirements">
    Le mot de passe doit contenir au moins 8 caractères, dont une majuscule, une minuscule et un chiffre.
  </div>
  <div id="password-strength" aria-live="polite"></div>
</div>
```

```javascript
function checkPasswordStrength(password) {
  const strength = document.getElementById('password-strength');
  const regex = /^(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{8,}$/;
  
  if (password.length === 0) {
    strength.textContent = '';
  } else if (password.length < 8) {
    strength.textContent = 'Mot de passe trop court';
  } else if (!regex.test(password)) {
    strength.textContent = 'Mot de passe moyen';
  } else {
    strength.textContent = 'Mot de passe fort';
  }
}

function togglePasswordVisibility() {
  const passwordInput = document.getElementById('password');
  const toggleButton = document.querySelector('.toggle-password');
  const showIcon = toggleButton.querySelector('.show-password');
  const hideIcon = toggleButton.querySelector('.hide-password');
  
  if (passwordInput.type === 'password') {
    passwordInput.type = 'text';
    showIcon.hidden = true;
    hideIcon.hidden = false;
    toggleButton.setAttribute('aria-label', 'Masquer le mot de passe');
  } else {
    passwordInput.type = 'password';
    showIcon.hidden = false;
    hideIcon.hidden = true;
    toggleButton.setAttribute('aria-label', 'Afficher le mot de passe');
  }
}
```

## Exercice 3 : Projet final - Refonte du site Microforce

Pour cet exercice, nous allons nous concentrer sur la refonte de la page d'accueil du site Microforce (https://www.microforce.fr/) en mettant l'accent sur l'accessibilité et la sémantique HTML.

Voici les étapes à suivre :

1. Analysez la structure actuelle de la page d'accueil de Microforce.
2. Identifiez les principaux éléments et sections de la page.
3. Créez une nouvelle structure HTML sémantique et accessible.
4. Assurez-vous que tous les éléments interactifs sont accessibles au clavier.
5. Ajoutez des attributs ARIA appropriés lorsque nécessaire.

Voici un exemple de structure HTML pour la page d'accueil refondée :

```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Microforce - Experts Salesforce</title>
</head>
<body>
  <header>
    <a href="#main-content" class="skip-link">Aller au contenu principal</a>
    <img src="logo.png" alt="Logo Microforce">
    <nav aria-label="Navigation principale">
      <ul>
        <li><a href="#">Accueil</a></li>
        <li><a href="#">Services</a></li>
        <li><a href="#">Expertise</a></li>
        <li><a href="#">À propos</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </nav>
  </header>

  <main id="main-content">
    <h1>Experts Salesforce à votre service</h1>
    
    <section aria-labelledby="nos-services">
      <h2 id="nos-services">Nos services</h2>
      <ul>
        <li>Conseil Salesforce</li>
        <li>Intégration Salesforce</li>
        <li>Développement sur mesure</li>
        <li>Formation Salesforce</li>
      </ul>
    </section>

    <section aria-labelledby="pourquoi-nous-choisir">
      <h2 id="pourquoi-nous-choisir">Pourquoi nous choisir ?</h2>
      <ul>
        <li>Expertise reconnue</li>
        <li>Approche sur mesure</li>
        <li>Accompagnement personnalisé</li>
        <li>Résultats garantis</li>
      </ul>
    </section>

    <section aria-labelledby="temoignages">
      <h2 id="temoignages">Témoignages clients</h2>
      <ul>
        <li>
          <blockquote>
            <p>Microforce a transformé notre utilisation de Salesforce. Leur expertise a été cruciale pour notre succès.</p>
            <cite>Jean Dupont, PDG de TechCorp</cite>
          </blockquote>
        </li>
        <!-- Ajoutez d'autres témoignages ici -->
      </ul>
    </section>

    <section aria-labelledby="contactez-nous">
      <h2 id="contactez-nous">Contactez-nous</h2>
      <form action="/submit-form" method="post">
        <label for="name">Nom :</label>
        <input type="text" id="name" name="name" required>

        <label for="email">Email :</label>
        <input type="email" id="email" name="email" required>

        <label for="message">Message :</label>
        <textarea id="message" name="message" required></textarea>

        <button type="submit">Envoyer</button>
      </form>
    </section>
  </main>

  <footer>
    <p>&copy; 2025 Microforce - Tous droits réservés</p>
    <nav aria-label="Liens utiles">
      <ul>
        <li><a href="#">Mentions légales</a></li>
        <li><a href="#">Politique de confidentialité</a></li>
        <li><a href="#">Plan du site</a></li>
      </ul>
    </nav>
  </footer>
</body>
</html>
```