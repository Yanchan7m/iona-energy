# IONA ENERGY

Site vitrine pour un **intermédiaire en produits pétroliers**. Trois scènes 3D
(barils EN590, parc de stockage type Vopak, pétrolier FOB) rendues en **WebGL
via Three.js** et pilotées par le scroll.

## Lancer le site

Aucune dépendance, aucun build : Three.js est **inliné** dans `index.html`.

- Double-clique sur `index.html`, **ou**
- sers le dossier pour un rendu optimal :

```bash
python3 -m http.server 8000
# puis ouvre http://localhost:8000
```

## Mettre en ligne

Le site est servi sur **https://iona.axone-capital.com**.

### GitHub Pages

GitHub Pages sur un repo **privé** nécessite un compte GitHub Pro. Repo public :
*Settings → Pages → Branch: `main` / root → Save*.

Le fichier `CNAME` à la racine déclare déjà le domaine. Côté DNS d'`axone-capital.com`,
ajouter un enregistrement :

```
Type   Nom     Valeur
CNAME  iona    yanchan7m.github.io.
```

Puis dans *Settings → Pages → Custom domain*, saisir `iona.axone-capital.com` et
cocher **Enforce HTTPS** une fois le certificat émis (quelques minutes).

### Autre hébergeur

Netlify, Vercel ou Cloudflare Pages fonctionnent aussi : déployer le dossier tel
quel et pointer le sous-domaine `iona` vers l'hébergeur (le fichier `CNAME` est
alors ignoré, la config se fait dans le dashboard).

## Structure

```
index.html   # le site complet (HTML + CSS + Three.js inliné)
CNAME        # domaine personnalisé pour GitHub Pages
PROMPT.md    # prompt de génération pour la version framework (Next.js/R3F)
```

## Contenu

- **3 scènes 3D** au scroll : barils (EN590 / JET A-1 / D6 / Crude), tank farm
  « Vopak to Vopak · tank to tank », pétrolier FOB sur mer animée.
- Sections : Produits, Procédure (ICPO → CIS/POF → POP → SGS / Dip Test →
  Dip & Pay / TTT), Hubs (Rotterdam · Fujairah), contact.
- Thème sombre, responsive, `prefers-reduced-motion` respecté.

## Personnaliser

- Couleurs : variables CSS en haut de `index.html` (`--accent`, `--ink`…).
- Textes : directement dans le HTML des sections.
- 3D : les fonctions `makeBarrel`, `makeTank`, l'acte pétrolier et les poses
  caméra sont dans le `<script>` en bas de `index.html`.
