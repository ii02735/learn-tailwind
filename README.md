# Tailwind

Tailwind est un **framework CSS** comme Bootstrap. 
La principale différence est qu'il n'y a pas de **composants prédéfinis / classes de haut-niveaux**, comme des boutons, des alertes, etc.

C'est au développeur de rédiger des classes s'il en a besoin. Cependant, Tailwind possède des classes utilitaires pour gérer **l'agencement des blocs** (margin, padding, etc.).

## Moyens d'installation

Nous allons passer par **NPM** :

```sh
npm i -D tailwindcss
npx tailwindcss init
```

Mais il existe d'autres moyens, consulter la documentation : https://tailwindcss.com/docs/installation.

La commande d'initialisation va créer un fichier **tailwind.config.js**.

## Le fichier de configuration

Le fichier tailwind.config.js permet **d'étendre la configuration de tailwind**, comme ajouter des couleurs personnalisées par exemple.

La structure du fichier va ressembler à celle-ci : 

```js
module.exports = {
    content: [],
    theme: {
    	extend: {}
    },
    plugins: []
}
```

**L'attribut `content` est important** : il permet d'informer à Tailwind, quel est le contenu qui doit embarquer le style de Tailwind (un fichier HTML par exemple).

### Ajouter les directives Tailwind dans une feuille de style

Pour permettre à Tailwind de construire correctement les règles CSS, il faut ajouter les directives dans une feuille CSS : 

```css
/* style.css */
@tailwind base;
@tailwind components;
@tailwind utilities;
```

## La construction sous NPM

Pour construire son style, exécuter la commande NPM suivante : 

```
npx tailwind -i <style contenant les direcives + CSS custom> -o <feuille de style finale> --watch
```

## Personnalisation de tailwind

Voici des exemples permettant de personnaliser le fonctionnement du framework.

### Préciser des dimensions personnalisées pour les écrans

Similairement à Bootstrap, Tailwind propose une panoplie de classes utilitaires qui vont s'appliquer sur des **dimensions d'écrans spécifiques**.

On peut **écraser les dimensions d'écrans par nos propres valeurs** :

```js
module.exports = {
    content: [],
    theme: {
        screens: {
           sm: '480px', // La nouvelle dimension pour de petits écrans commencera à partir de 480px
           md: '780px',
           lg: '1000px'
        }
    	extend: {}
    },
    plugins: []
}
```

### Préciser des couleurs personnalisées

Tailwind possède plusieurs **classes CSS de couleurs**.

Il est cependant possible de préciser nos propres classes de couleurs : 

```js
module.exports = {
    content: [],
    theme: {
    	extend: {
    	   colors: {
    	     specialCrimson: '#DC143C"
    	   }
    	}
    },
    plugins: []
}
```
