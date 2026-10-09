# Sans Concession — maquette de test (Convtek)

Reproduction fidele de la landing page Google Ads `sans-concession.fr/lp/[ville]/vendre`,
utilisee pour faire relire les variantes de test avant toute mise en ligne.

Le selecteur en bas a gauche bascule entre la version actuelle (A) et la variante (B)
pour chacun des deux tests.

- Test 1, haut de page : promesse chiffree, carrousel des trois vehicules, barre de preuve
- Test 2, reassurance : bloc sous le formulaire, deux messages remis sur mobile, bloc questions

Aucune donnee n'est envoyee : le formulaire est fonctionnel a l'ecran mais ne transmet rien.
Page en `noindex`, non referencee.

## Republier apres une modification

Depuis `05-Exports/sans-concession-reproduce-lp-ads` :

```
npx vite build --base=./
node scripts/chemins-relatifs.mjs
```

puis copier le contenu de `dist/` ici et pousser.

Les deux etapes sont necessaires. `--base=./` parce que Git Bash sous Windows
convertit un `--base=/sans-concession-preview/` en chemin Windows et la page
sort blanche. Le script parce que Vite ne reecrit pas les chemins `/images/`
et `/anim/` ecrits en dur dans le code, qui sinon sont cherches a la racine du
domaine et renvoient 404 sur chaque image.
