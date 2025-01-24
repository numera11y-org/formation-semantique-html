# Images et médias accessibles

## Alternatives textuelles pertinentes

Les alternatives textuelles sont essentielles pour rendre les images et autres contenus non textuels accessibles à tous les utilisateurs, en particulier ceux qui utilisent des lecteurs d'écran ou qui ont des difficultés visuelles.

Points clés :
- Chaque image doit avoir un attribut `alt` avec un texte descriptif pertinent
- Le texte alternatif doit transmettre la même information ou fonction que l'image
- Pour les images décoratives, utiliser un attribut `alt` vide (`alt=""`)
- Les alternatives doivent être concises mais complètes

## Sous-titres et transcriptions pour les contenus audio/vidéo

Les sous-titres et transcriptions rendent les contenus audio et vidéo accessibles aux personnes sourdes ou malentendantes, ainsi qu'à celles qui ne peuvent pas écouter le son.

Points clés :
- Fournir des sous-titres synchronisés pour tous les contenus audio préenregistrés
- Proposer des transcriptions textuelles pour les contenus audio et vidéo
- Les sous-titres doivent inclure les dialogues et les informations sonores importantes
- Utiliser des formats de sous-titres standards comme WebVTT

## Images complexes et diagrammes accessibles

Les images complexes, graphiques et diagrammes nécessitent une attention particulière pour être rendus accessibles.

Points clés :
- Fournir une description textuelle détaillée de l'image complexe
- Utiliser des légendes et des explications dans le texte environnant
- Pour les graphiques, fournir les données sous forme de tableau accessible
- Envisager des versions alternatives simplifiées pour les diagrammes complexes

## Exercices et corrigés

### Exercice 1 : Alternatives textuelles

Proposez des alternatives textuelles pertinentes pour les images suivantes :

1. Logo de l'entreprise en en-tête du site
2. Icône de panier d'achat
3. Photo d'illustration d'un article de blog
4. Graphique montrant l'évolution des ventes sur 5 ans

Corrigé :

1. `alt="Nom de l'entreprise"`
2. `alt="Panier d'achat"`
3. `alt=""` (si purement décorative) ou brève description si pertinente
4. `alt="Graphique : Évolution des ventes de 2018 à 2022"` (avec description détaillée dans le texte ou en légende)

### Exercice 2 : Sous-titres vidéo

Voici un extrait de dialogue d'une vidéo. Proposez des sous-titres appropriés :

[Bruit de porte qui s'ouvre]
Jean : Bonjour Marie, comment vas-tu aujourd'hui ?
Marie : (en chuchotant) Chut ! Le bébé dort enfin.

Corrigé :

```
[Porte s'ouvre]
Jean : Bonjour Marie, comment vas-tu aujourd'hui ?
Marie : (chuchote) Chut ! Le bébé dort enfin.
```

### Exercice 3 : Description d'image complexe

Décrivez de manière accessible le diagramme suivant :
[Un organigramme montrant la structure d'une entreprise avec 3 niveaux hiérarchiques et 5 départements]

Corrigé :

```html
<img src="organigramme.jpg" alt="Organigramme de l'entreprise XYZ" />
<p>Description de l'image : L'organigramme montre la structure hiérarchique de l'entreprise XYZ sur 3 niveaux. Au sommet se trouve le PDG. Le deuxième niveau comprend 3 directeurs : Finances, Opérations et Marketing. Le troisième niveau montre 5 départements : Comptabilité et RH sous Finances, Production et Logistique sous Opérations, et Ventes sous Marketing.</p>
```