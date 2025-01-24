# Sémantique des éléments interactifs

## Liens et boutons sémantiques

Les liens et boutons doivent être clairement identifiables et leur fonction doit être évidente pour tous les utilisateurs. Voici les points clés à respecter :

- Utiliser les balises appropriées : `<a>` pour les liens et `<button>` pour les boutons
- Fournir un texte descriptif clair pour chaque lien et bouton
- Différencier visuellement les liens du texte normal (par exemple, par le soulignement)
- Utiliser des verbes d'action pour les boutons (ex: "Envoyer", "Rechercher")
- Éviter les liens avec le texte "Cliquez ici" ou "En savoir plus"

## Formulaires accessibles

Les formulaires doivent être conçus pour être faciles à comprendre et à utiliser pour tous. Voici les principales règles à suivre :

- Associer chaque champ à une étiquette (`<label>`) explicite
- Regrouper les champs liés avec `<fieldset>` et `<legend>`
- Indiquer clairement les champs obligatoires
- Fournir des instructions claires sur le format attendu (ex: date, téléphone)
- Positionner les étiquettes de manière cohérente (au-dessus ou à gauche des champs)
- Utiliser des messages d'erreur précis et positionnés près des champs concernés

## Tableaux de données structurés

Les tableaux doivent présenter les informations de manière claire et compréhensible :

- Utiliser `<th>` pour les en-têtes de colonnes et de lignes
- Ajouter un résumé avec l'attribut `summary` sur `<table>` (pour les tableaux complexes)
- Utiliser `<caption>` pour donner un titre au tableau
- Associer les cellules à leurs en-têtes avec `scope`, `id` et `headers`
- Éviter d'utiliser les tableaux pour la mise en page

## Exercices et corrigés

### Exercice 1 : Liens et boutons sémantiques

Corrigez le code HTML suivant pour améliorer la sémantique des liens et boutons :

```html
<div onclick="location.href='accueil.html'">Retour à l'accueil</div>
<div class="bouton">Soumettre le formulaire</div>
<a href="#" onclick="document.forms[0].submit()">Envoyer</a>
```

Corrigé :

```html
<a href="accueil.html">Retour à l'accueil</a>
<button type="submit">Soumettre le formulaire</button>
<button type="submit">Envoyer</button>
```

### Exercice 2 : Formulaire accessible

Améliorez l'accessibilité du formulaire suivant :

```html
<form>
  Nom : <input type="text" name="nom">
  Email : <input type="text" name="email">
  <input type="checkbox" name="newsletter"> Recevoir la newsletter
  <input type="submit" value="OK">
</form>
```

Corrigé :

```html
<form>
  <div>
    <label for="nom">Nom :</label>
    <input type="text" id="nom" name="nom" required>
  </div>
  <div>
    <label for="email">Email :</label>
    <input type="email" id="email" name="email" required>
  </div>
  <div>
    <input type="checkbox" id="newsletter" name="newsletter">
    <label for="newsletter">Recevoir la newsletter</label>
  </div>
  <button type="submit">S'inscrire</button>
</form>
```