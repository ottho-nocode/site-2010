# site-2010

Skill Claude Code qui refait un site actuel comme s'il avait été créé en 2010 : largeur fixe, dégradés brillants, faux plug-in Flash, compteur de visiteurs, livre d'or avec smileys, captcha et badges « W3C XHTML 1.0 valide ».

Le skill part du vrai contenu du site (offres, prix, avis clients), construit 5 pages en HTML statique, les vérifie par captures d'écran, puis les met en ligne sur Vercel si tu es d'accord.

Exemples :
- https://boulangerie-durand.vercel.app/ (style artisanal)
- https://ottho-2010.vercel.app/ (style Web 2.0)

## Installation

Dans Claude Code :

```
/plugin marketplace add ottho-nocode/site-2010
/plugin install site-2010@site-2010
```

Sans le système de plugins, copie le dossier du skill dans tes skills personnels :

```bash
git clone https://github.com/ottho-nocode/site-2010.git
cp -R site-2010/skills/site-2010 ~/.claude/skills/
```

## Prérequis

- **Claude Code**.
- **Python 3** pour le serveur local (déjà présent sur Mac).
- **Pour les captures de vérification** : le MCP Playwright ou Claude in Chrome (conseillé).
- **Pour la mise en ligne** : un compte Vercel gratuit et la CLI (`npm i -g vercel`, puis `vercel login`).

## Utilisation

Ouvre Claude Code dans un dossier vide, puis :

```
/site-2010 https://ton-site.fr
```

Ou simplement : « refais mon site https://ton-site.fr en mode 2010 ».

Compte 20 à 40 minutes. Claude te montre les captures avant toute mise en ligne, et te renvoie ensuite l'adresse `https://[nom]-2010.vercel.app`.

## Bon à savoir

- **Ne transforme que ton propre site**, ou celui d'un client qui t'a donné son accord : le résultat reprend son nom, son logo et ses avis clients.
- **Les formulaires n'envoient rien.** Le site est une vitrine humoristique, pas un vrai site de contact.
- **Pas de version mobile.** En 2010, un site faisait 960px de large, point.

## Contenu

```
skills/site-2010/
├── SKILL.md              méthode en 7 étapes
└── templates/
    ├── style.css         feuille de style Web 2.0 (palette à remplacer)
    ├── page.html         squelette commenté d'une page
    ├── snippets.html     blocs pour les pages intérieures
    └── assets/           motif de fond, étoile, coche, avatar
```

Licence MIT. Un skill [Ottho](https://ottho.co).
