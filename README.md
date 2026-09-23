# Fractal Addon for Blender

**Fractal Addon** est un générateur de fractales 3D pour Blender fondé sur une **coupole de Johnson modifiée**. La base carrée de la construction d'origine est remplacée par une base polygonale paramétrable, puis la structure est répétée selon un ordre d'itération choisi.

> English summary: a Blender add-on that generates recursive 3D geometry from a modified Johnson cupola with a configurable even-sided polygonal base.

## Principe géométrique

La construction part d'une coupole inspirée des solides de Johnson. Le carré de base est généralisé en un polygone, ce qui permet de produire plusieurs familles de formes avec le même processus récursif.

Dans l'implémentation actuelle, la génération fonctionne uniquement avec des polygones possédant un **nombre pair de côtés**.

```text
polygone pair
      ↓
coupole modifiée
      ↓
répétition récursive
      ↓
fractale 3D
```

## Cas d'utilisation

- générer des objets fractals dans Blender ;
- explorer les variations d'une coupole polygonale ;
- produire des formes décoratives ou expérimentales ;
- préparer des objets pour une étude d'impression 3D ;
- comprendre la croissance récursive d'une géométrie.

## Installation

1. Téléchargez le dépôt au format ZIP.
2. Dans Blender, ouvrez **Edit > Preferences > Add-ons**.
3. Utilisez **Install from Disk**.
4. Sélectionnez l'archive puis activez l'add-on.
5. Ouvrez son panneau dans la barre latérale de la vue 3D.

## Utilisation rapide

1. Ouvrez le panneau Fractal Addon.
2. Choisissez la longueur ou l'échelle de départ.
3. Sélectionnez un polygone possédant un nombre pair de côtés.
4. Définissez un ordre d'itération faible pour le premier essai.
5. Cliquez sur **Generate**.
6. Inspectez le résultat et contrôlez le nombre d'objets et de sommets.
7. Utilisez **Merge by Distance** lorsque des sommets superposés doivent être fusionnés.
8. Nettoyez puis renommez la géométrie finale.

## Pourquoi limiter l'ordre d'itération ?

La quantité de géométrie augmente rapidement à chaque niveau. Un ordre élevé peut saturer la mémoire, ralentir fortement Blender ou provoquer un plantage.

Procédure recommandée :

- commencez à l'ordre 1 ou 2 ;
- enregistrez votre fichier avant d'augmenter l'ordre ;
- surveillez le nombre d'objets, de sommets et l'utilisation mémoire ;
- augmentez une seule valeur à la fois ;
- interrompez la génération si la scène devient instable.

## Nettoyage du maillage

Après la génération :

1. joignez les éléments qui doivent former un seul objet ;
2. passez en mode Édition ;
3. sélectionnez les sommets concernés ;
4. utilisez **Merge by Distance** ;
5. contrôlez les normales et les éventuelles faces internes ;
6. vérifiez que le maillage répond à votre usage final.

Cette étape est particulièrement importante avant une opération booléenne ou une impression 3D.

## Questions fréquentes

### Comment créer une fractale 3D dans Blender ?

Installez l'add-on, choisissez une base polygonale paire, définissez une longueur et un ordre faible, puis lancez la génération.

### Pourquoi les polygones impairs ne fonctionnent-ils pas ?

L'algorithme actuel dépend des correspondances symétriques de la coupole modifiée. Ces correspondances sont définies pour une base possédant un nombre pair de côtés.

### Pourquoi Blender ralentit-il pendant la génération ?

La récursion multiplie rapidement le nombre d'éléments géométriques. Réduisez l'ordre d'itération et testez progressivement les limites de votre machine.

### Pourquoi faut-il utiliser Merge by Distance ?

Certaines étapes génèrent des sommets occupant la même position. **Merge by Distance** permet de les fusionner afin d'obtenir un maillage plus propre et plus facile à modifier.

### Peut-on imprimer directement la fractale ?

Pas sans contrôle préalable. Vérifiez l'échelle, l'épaisseur, les normales, les intersections et l'étanchéité du maillage.

### Quelle est la différence avec le modèle fractal universel ?

Cet add-on est un générateur Blender construit autour d'une coupole polygonale. Le [modèle fractal universel](https://github.com/E1LaeTID/Un-modele-fractale-universel) formalise plus largement la substitution d'un motif sur des segments.

### Où trouver l'outil avec les autres générateurs ?

[CoTQoQ Builder](https://github.com/E1LaeTID/CoTQoQ_builder) regroupe les quatre add-ons Blender.

## Apprendre Blender

Une [formation Blender destinée aux débutants](https://www.udemy.com/course/modelisation-impression-3d-avec-blender-tous-niveaux/?couponCode=LETSLEARNNOW) accompagne la modélisation et l'impression 3D. Elle permet d'utiliser les générateurs comme point de départ avant d'effectuer des modifications manuelles plus avancées.

## Écosystème

- [CoTQoQ Builder](https://github.com/E1LaeTID/CoTQoQ_builder)
- [3D Tool Helper](https://github.com/E1LaeTID/3DToolHelperForBlender)
- [Maze Builder](https://github.com/E1LaeTID/BlenderMazeBuilderAddon)
- [Politron Builder](https://github.com/E1LaeTID/BlenderPolitronAddon)
- [Modèle fractal universel](https://github.com/E1LaeTID/Un-modele-fractale-universel)
- [Portail E1LaeTID](https://e1laetid.github.io/)

## Statut et licence

Prototype fonctionnel. Le code est distribué sous **Apache License 2.0** ; consultez le fichier [LICENSE](LICENSE).
