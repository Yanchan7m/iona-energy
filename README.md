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

## Mettre en ligne (GitHub Pages)

GitHub Pages sur un repo **privé** nécessite un compte GitHub Pro. Si tu passes
le repo en public : *Settings → Pages → Branch: `main` / root → Save*. L'URL sera
`https://Yanchan7m.github.io/iona-energy`.

Sinon, tout hébergeur statique fonctionne (Netlify, Vercel, Cloudflare Pages) :
il suffit de déployer le dossier tel quel.

## Structure

```
index.html   # le site complet (HTML + CSS + Three.js inliné)
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
