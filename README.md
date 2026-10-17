# Portfolio – Anaïs Logerais, étudiante infirmière

Site portfolio bilingue (français / anglais) : parcours, stages, compétences, CV à télécharger et formulaire de contact.

**Site en ligne :** https://alifsicrip.github.io/al-ide/

Site statique en HTML et CSS pur, sans framework ni étape de build. Il peut être installé sur l'écran d'accueil d'un mobile (PWA).

## Arborescence

```
al-ide/
├── index.html          Version française
├── en.html             Version anglaise
├── manifest.json       Configuration PWA (nom, icônes, couleurs)
├── README.md
├── assets/
│   ├── logo.png                        Logo affiché dans l'en-tête
│   ├── favicon.ico                     Icône d'onglet
│   ├── portfolio-v4-purple-180.png     Icône Apple (écran d'accueil iOS)
│   ├── portfolio-v4-purple-192.png     Icône PWA / Android
│   └── portfolio-v4-purple-512.png     Icône PWA grande taille
└── cv/
    ├── CV-Anais-Logerais-FR.pdf
    └── CV-Anais-Logerais-EN.pdf
```

Les noms des fichiers PDF doivent rester identiques, car les boutons de téléchargement de la page CV pointent dessus.

## Personnaliser le contenu

Tout le texte à compléter est entre crochets `[ ... ]` dans `index.html` et `en.html` : année de formation, nom de l'IFSI, stages, compétences, texte « À propos ».

Pense à modifier **les deux fichiers** pour garder les versions FR et EN cohérentes.

### Formulaire de contact

Le formulaire utilise [Formspree](https://formspree.io). Dans les deux fichiers, remplace `VOTRE_ID_FORMSPREE` dans l'attribut `action` par l'identifiant de ton formulaire :

```html
<form action="https://formspree.io/f/VOTRE_ID_FORMSPREE" method="POST">
```

Tant que ce n'est pas fait, l'envoi du formulaire ne fonctionne pas.

## Couleurs

Les couleurs sont définies en haut de chaque fichier, dans le bloc `:root`.

| Variable | Valeur | Usage |
|---|---|---|
| `--dark` | `#1d4e5b` | Texte, boutons, pied de page |
| `--hero` | `#09637C` | Bandeau d'accueil, titres |
| `--light` | `#029aa3` | Bordures, survols |
| `--purple` | `#7B3FA0` | Mots surlignés (`.hl`) |
| `--violet` | `#6b526c` | Dates, pastilles « savoir-être » |
| `--grey` | `#B5B7BB` | Textes secondaires |
| `--bg` | `#f5fafd` | Fond de page |

Pour changer la couleur des mots surlignés, modifie uniquement la valeur de `--purple`.

## Icônes et PWA

Le bloc suivant est présent dans le `<head>` des deux pages :

```html
<link rel="icon" href="/al-ide/assets/favicon.ico" sizes="any">
<link rel="icon" type="image/png" sizes="192x192" href="/al-ide/assets/portfolio-v4-purple-192.png">
<link rel="apple-touch-icon" href="/al-ide/assets/portfolio-v4-purple-180.png">
<link rel="manifest" href="/al-ide/manifest.json">
<meta name="theme-color" content="#1D4F5C">
```

Les chemins commencent par `/al-ide/` car le site est servi depuis un sous-dossier de GitHub Pages. Si le dépôt est renommé, ou le site déplacé vers un domaine personnalisé, ces chemins et ceux de `manifest.json` doivent être adaptés.

## Publication (GitHub Pages)

1. Pousser tous les fichiers et dossiers sur la branche `main`.
2. Dans **Settings → Pages**, choisir la branche `main`, dossier `/ (root)`.
3. Attendre 1 à 2 minutes : le site est disponible à l'adresse indiquée en haut de ce fichier.

## Vérifier après publication

- L'icône apparaît dans l'onglet du navigateur.
- Le logo s'affiche en haut à gauche.
- Les deux boutons CV téléchargent bien les PDF.
- Le bouton **EN / FR** bascule entre les deux versions.
- Sur mobile (Chrome Android) : menu ⋮ → **Ajouter à l'écran d'accueil**.
