---
name: site-2010
description: Transforme un site actuel en version rétro « façon 2010 » à partir de son vrai contenu (HTML statique XHTML, largeur fixe 960px, dégradés brillants Web 2.0, faux plug-in Flash, compteur de visiteurs, livre d'or, captcha), le vérifie par captures d'écran, puis le met en ligne sur Vercel après accord. À utiliser quand l'utilisateur demande « refais mon site en mode 2010 », « version rétro de mon site », « mon site comme en 2010 », « site old school », ou tape /site-2010. Argument attendu : l'URL du site à transformer.
---

# site-2010

Refait un site actuel comme s'il avait été créé en 2010. Le résultat est un site statique de 5 pages environ, prêt à mettre en ligne sur Vercel.

Exemples réalisés avec ce skill (à ouvrir pour s'imprégner du style, pas pour copier le contenu) :
- https://boulangerie-durand.vercel.app/ : petit commerce, style artisanal chaleureux.
- https://ottho-2010.vercel.app/ : entreprise de services en ligne, style Web 2.0 brillant.

## Entrées

- **URL du site actuel** (obligatoire). Si elle manque, demande-la avant toute chose.
- **Nom court** pour le projet Vercel. Si absent, déduis-le du domaine (`ottho.co` donne `ottho`).

Ne transforme que le site de l'utilisateur, ou celui d'un client qui a donné son accord : le résultat reprend le nom, le logo et les avis clients. En cas de doute, pose la question.

Travaille dans un dossier vide. S'il ne l'est pas, signale-le et ne mets jamais en ligne les fichiers que tu n'as pas créés.

## Fichiers fournis (dans le dossier de ce skill)

- `templates/style.css` : feuille de style complète du style Web 2.0. L'en-tête liste les couleurs à remplacer.
- `templates/page.html` : squelette commenté d'une page d'accueil (bandeau, menu, flash info, deux colonnes, pied).
- `templates/snippets.html` : blocs pour les pages intérieures (tableau de tarifs, comparatif, étapes, livre d'or, formulaires, chiffres clés).
- `templates/assets/` : `fond.svg` (motif de fond), `etoile.svg` (étoile « Nouveau ! »), `coche.svg`, `avatar.svg` (silhouette « photo bientôt disponible »).

## Étape 1 : récupérer le vrai contenu

1. Télécharge la page d'accueil et 2 ou 3 pages clés avec `curl`, puis extrais le texte (retire `<script>` et `<style>`).
2. Relève : offres, prix, dates à venir, avis clients avec les noms tels que publiés, liens vers les réseaux sociaux, mentions légales, couleur principale, logo (SVG ou favicon).
3. N'invente aucun chiffre, aucun prix, aucun numéro de téléphone, aucune adresse, aucun avis. Si une information manque, laisse-la de côté.

## Étape 2 : choisir le style

- **Web 2.0** (services, tech, formation, en ligne) : copie `templates/style.css` et remplace la palette violette par la couleur principale de la marque, en gardant les mêmes écarts de clarté. Recolore `fond.svg`.
- **Artisanal** (commerce de proximité, restaurant, artisan) : télécharge `https://boulangerie-durand.vercel.app/style.css` comme base et adapte ses couleurs. Reprends aussi les noms de classes de `templates/snippets.html` qui manquent.

## Étape 3 : construire

Règles techniques, toutes obligatoires :
- HTML statique : un fichier `.html` par page, un seul `style.css`, un dossier `assets/`. Pas de framework, pas de npm, pas de build.
- Doctype XHTML 1.0 Transitional, balises en minuscules, `<br />` fermés.
- Largeur fixe 960px centrée, mise en page en `float`. Pas de flexbox, pas de grid, aucune adaptation mobile.
- Texte en Verdana 11px, titres en Trebuchet MS. Une seule police Google Fonts d'époque (Lobster ou Yanone Kaffeesatz) pour le logo ou un badge.
- Bandeau, menu et pied recopiés dans chaque fichier, comme à l'époque.
- Images : clip-arts SVG dessinés par toi (contour sombre épais, dégradés, petit reflet blanc). Pas de photo de banque d'images, pas d'emoji.
- JavaScript : petits scripts inline seulement. Les formulaires n'envoient rien : à la validation, ils se masquent et affichent un message de confirmation.

Pages type : Accueil, Offres (ou Produits), Présentation (ou Méthode, Qui sommes-nous), Livre d'or, Contact. 6 rubriques au maximum dans le menu.

Structure de chaque page : voir `templates/page.html`. Colonne principale de 620px à gauche, colonne de 270px à droite avec 4 à 7 blocs empilés.

## Étape 4 : les clins d'œil 2010 (au moins 8)

- Faux diaporama Flash : « Plug-in manquant », bouton « Télécharger Flash Player ».
- Phrase de bienvenue en Comic Sans : « ~ Bienvenue sur le site de ... ! ~ ».
- Bandeau « Flash info » avec `<marquee>` et « Dernière mise à jour : JJ/MM/2010 ».
- Compteur de visiteurs (chiffres verts sur fond noir) « depuis le 01/01/2010 ».
- « NOUVEAU ! » qui clignote dans un encadré en pointillés.
- Étoile ou badge rond qui pulse dans le bandeau (« Gratuit ! », « Depuis 1987 »).
- Nuage de tags.
- Livre d'or avec les vrais avis (« Message n°X posté par ... le ... »), pagination, formulaire avec smileys et captcha.
- Formulaire de contact avec captcha, « Comment nous avez-vous connus ? (Yahoo!, annuaire...) », boutons Envoyer et Effacer.
- Boutons « Suivez-nous sur Twitter », YouTube, LinkedIn aux couleurs d'époque, vers les vrais comptes.
- Lettre d'information avec le texte « Votre adresse e-mail » qui s'efface au clic.
- « Site optimisé pour Internet Explorer 7 en 1024 x 768 ».
- Mini-badges 80x15 dans le pied : W3C XHTML 1.0, CSS valide, Firefox, RSS.

## Étape 5 : rédaction

- Ton d'une petite entreprise de 2010 : enthousiaste, un peu naïf (« N'hésitez pas à nous contacter ! »).
- Dates en 2010 partout : copyright, mises à jour, prochaines dates (garde le jour et le mois réels). Les anachronismes amusants peuvent rester.
- Orthographe et accents corrects. Aucun tiret long (— ou –) dans le texte : virgule, deux-points ou parenthèses.
- Les vrais boutons d'action (rendez-vous, commande, espace client) pointent vers les vraies pages du site actuel.
- Dernière ligne du pied de chaque page : « Version rétro et parodique du site [domaine], imaginée comme en 2010. Aucun formulaire n'envoie de message. » Si les avis ont des dates inventées, ajoute-le.

## Étape 6 : vérification

1. Lance un serveur local en arrière-plan : `python3 -m http.server 3100`.
2. Fais une capture d'écran pleine page de chaque page (fenêtre de 1100px de large) avec le MCP Playwright ou Claude in Chrome.
3. Corrige les défauts connus :
   - Liste à coches posée à côté d'une photo flottante : les coches disparaissent. `ul.coches` doit garder `overflow: hidden`.
   - Les trois boîtes d'offres n'ont pas la même hauteur : raccourcis la ligne `.infos` pour qu'elle tienne sur une ligne.
   - Colonne principale beaucoup plus courte que la colonne de droite : ajoute une section (« Pourquoi nous choisir ? » avec liste à coches) ou retire un bloc de la colonne.
   - Texte qui se coupe mal dans un tableau (« : » en début de ligne) : insère un `<br />`.
4. Vérifie qu'aucun lien interne ni aucune image n'est cassé, et qu'aucun tiret long ne reste (`grep -n "[—–]" *.html`).
5. Vérifie la console du navigateur : aucune erreur.
6. Montre les captures à l'utilisateur avant de passer à la mise en ligne.

## Étape 7 : mise en ligne sur Vercel (seulement après accord explicite)

La mise en ligne est publique : demande toujours l'accord avant.

1. Crée un `.vercelignore` **avant** `vercel link`. Exclus au minimum : `.env*`, `.vercel`, `.claude`, `*.md`, et tout fichier qui n'appartient pas au site. `vercel link` crée un `.env.local` qui contient un jeton : il ne doit jamais être publié.
2. Vérifie que le projet n'existe pas déjà avec des déploiements (`vercel ls [nom]-2010`). Ne réutilise jamais un projet existant sans accord.
3. `vercel link --yes --project [nom]-2010`, puis `vercel deploy --prod --yes`.
4. Contrôle avec `vercel inspect` que le statut est « Ready ».
5. Vérifie avec `curl` que chaque page répond en 200 et que les fichiers exclus (`.env.local`, notes) répondent en 404.
6. Donne l'adresse `https://[nom]-2010.vercel.app` à l'utilisateur. Si le dossier n'est pas un dépôt git, signale que la production tourne sur des fichiers locaux sans historique.
