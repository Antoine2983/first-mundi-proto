# Prototype MVP — parcours complet

Prototype cliquable d'une plateforme immobilière. **Un seul fichier, aucune dépendance, fonctionne hors ligne** : ouvre `index.html` dans un navigateur (double-clic).

**24 écrans · 67 états**, vérifiés sur toutes les combinaisons écran × état × mode × connecté/visiteur, en niveau de gris. Pas de direction artistique : on valide ici les **parcours, la hiérarchie de l'information et les états**. La couleur, la typo et le logo viennent après.

## Ce que contient le prototype

| Groupe | Écrans |
|---|---|
| **Parcours acquéreur** (10) | Accueil ⭐ · Recherche & résultats · Fiche bien ⭐ · Page agence · Mise en relation 1 & 2 · Vérification SMS · Favoris · Recherches sauvegardées · Paramètres |
| **Estimation & IA** (2) | Estimation + score + avis (bascule investisseur / acquéreur) · Complétude du profil acquéreur |
| **Côté agence** (6) | Choix du profil · Vérification SIRET · Tableau de bord · Mes biens · Fiche bien côté agence · Dépôt d'un bien (4 étapes) |
| **Leads & facturation** (5) | Mes leads · Fiche lead · Acheter une qualification · Paiements & factures · Déclaration de vente |
| **Site vitrine** (1) | Landing publique + waitlist |

## Les deux écrans qui portent le produit

### L'accueil change de métier en cours de vie — 6 états

Avant la première recherche, le formulaire **est** l'écran. Après, la home devient un **tableau de bord de chasse** : « qu'est-ce qui a bougé depuis mon dernier passage ? ». Le pari de mise en page : faire les deux **sans jamais déplacer quoi que ce soit** — trois zones fixes (barre de recherche · zone de reprise · preuve), seul le contenu du milieu change.

`Visiteur — première visite` · `Visiteur — de retour` · `Compte neuf` · `En chasse` · `Demande envoyée` · `Ça a bougé`

Les règles qui tiennent l'écran :

- **Un seul bloc primaire à la fois**, choisi par le fait le plus **périssable** — pas par le profil. Demande consultée > baisse de prix sur un favori > demande sans réponse à 48 h > nouveautés d'alerte > favoris à comparer > amorçage > visiteur. Ce qui n'est pas retenu descend en ligne secondaire. Quatre cartes « importantes » n'en font aucune.
- **Le suivi porte N statuts, pas un.** La demande partant à toutes les agences du bien, le suivi affiche une ligne par agence, chacune avançant à son rythme, et un compteur en tête : **« 1 sur 3 l'a ouverte »**. On n'affiche que ce qu'on sait — la demande est partie, l'agence l'a ouverte. Pas si elle a appelé. D'où un bouton « elle m'a répondu » **par agence**, seule façon honnête de fermer la boucle.
- **L'écart entre les agences est l'information.** Sur le même bien, à la même heure, avec la même demande, une agence a réagi et deux non. Aucun portail ne peut produire ce chiffre — il faudrait pour cela que les trois annonces se connaissent. On l'affiche, on ne le commente pas.
- **La bascule à 48 h ne survit que si l'acquéreur a décoché.** Envoyer aux trois la vide de son objet : il n'y a plus d'agence 2 à proposer. Elle garde tout son sens dans l'autre cas — une seule agence retenue, sans réponse, et l'on rappelle que celle qui a été écartée propose toujours le bien.
- **Le nudge compte arrive en 2ᵉ visite, jamais en 1ʳᵉ.** Il est alors mérité par un usage, donc argumentable : « cette recherche ne survivra pas à ce navigateur ».
- **Preuve montrable plutôt que compteur.** « 12 480 biens · 1 260 agences » est de la statistique. Trois preuves vérifiables la remplacent — une annonce par bien · le budget total, pas le prix · le classement ne s'achète pas.
- **Afficher des biens en état « En chasse » ne viole pas « aucune annonce sans critère »** : le critère existe, c'est sa recherche enregistrée. Ce qui reste interdit, c'est une grille « populaires » ou « coups de cœur ».

### Le tunnel de mise en relation est ouvert, et la demande part à toutes les agences

**L'app ne demande jamais de compte pour chercher, filtrer, ouvrir une fiche ou comparer.** Il n'est demandé que pour deux choses : voir le cashflow, et envoyer une demande. Et pour l'envoi, il arrive **à la fin du tunnel** — le visiteur remplit ses coordonnées, son projet, choisit ses agences, et ne rencontre la vérification SMS qu'au clic « Envoyer ». Les quatre champs de l'étape 1 *sont* le compte : rien à remplir deux fois. Le mur ne disparaît pas, il se déplace au moment où l'utilisateur a le plus à perdre en abandonnant.

**Un bien porte N mandats : la demande part aux N agences.** L'écran les liste et l'acquéreur **décoche** celles qu'il ne veut pas solliciter.

- **Tout est coché par défaut — décocher est le geste, cocher n'en est pas un.** Envoyer à une seule obligerait l'acquéreur à choisir entre des agences qu'il ne connaît pas, sur un critère qu'il n'a pas, et à recommencer si elle ne répond pas.
- **On affiche pourquoi on pourrait vouloir décocher** : le prix demandé par chacune et la nature du mandat. Aucun tri, aucun classement, aucune recommandation.
- **La dernière case se verrouille** — une demande sans destinataire n'est pas une demande. Elle refuse d'être décochée et le dit sur place, plutôt que d'échouer à l'envoi.
- **Le consentement nomme les destinataires retenus**, pas « nos partenaires ».
- **Bien à mandat unique** : pas de cases du tout, une phrase. Un état dédié le maquette.

### La recherche en langage naturel n'a pas d'écran

Le mode « Décrire » vit **entièrement dans la nav** — pilule dépliée (champ + suggestions + **Valider**), pilule repliée (la phrase saisie + **Valider**), et onglet ✦ Décrire dans la popup de recherche mobile. Les trois mènent à la même **popup d'interprétation** : les critères déduits en chips modifiables, deux questions fermées (jamais un chat ouvert), et le rappel — *« aucun prix ni rendement n'est estimé ici : j'interprète une demande, je ne chiffre rien »*.

## Le côté agence

- **Mes biens** — les colonnes actionnables sont la **complétude** et la **position de contact**, au même rang que le prix : ce sont les deux seules variables que l'agence contrôle et qui changent son classement sur un bien partagé.
- **Fiche bien côté agence** — complétude en **liste de gestes** (« il vous manque le plan et 4 photos », pas « 72 % »), position de contact expliquée par la règle publiée, sélecteur de statut en colonne collante : l'action la plus fréquente de la journée.
- **Mes leads** — la distinction gratuit / qualifié est rejouée partout. Le total à débloquer est une **information, pas un bouton** : la vente se fait à l'unité, un panier transformerait un achat réfléchi en regret.
- **Le lead sans réponse à 48 h est signalé à l'agence avant de l'être à l'acquéreur.** Le cacher serait déloyal ; le dire en fait le rappel le plus efficace du produit. « Nouveau » côté agence est exactement « Envoyée » côté acquéreur.
- **Un lead partagé le dit avant l'achat, jamais après.** L'acquéreur adresse sa demande à tous les mandataires du bien : plusieurs agences reçoivent le même lead et **chacune paie sa qualification au prix plein**. Ce qu'elle achète est une information sur l'acquéreur, pas une exclusivité sur lui — mais ça ne se défend que si c'est affiché avant le bouton. La mention « Partagé · N agences » est donc dans la liste, dans la fiche et dans l'écran d'achat, aperçu **et** récapitulatif de paiement. Un lead non partagé porte la mention inverse, « Vous seul » : une information qui n'apparaît que dans le mauvais cas se lit comme un avertissement.

## La règle des deux sources

**Aucune maquette n'affiche une donnée qui n'a pas de source dans le périmètre acté** : les champs du bien (type, prix, surface, pièces, localisation géocodée, DPE, photos, date de publication) et les mutations notariales publiques (DVF) pour l'estimation.

Écartés : écoles, secteur scolaire, transports, commerces, temps de trajet. Toute donnée exigeant une nouvelle ingestion reste dehors, y compris quand elle serait utile.

Trois limites matérialisées : la **carte de la fiche est statique** (recherche cartographique hors périmètre) · le bloc **« Le quartier »** ne dit que ce que les ventes publiques disent · **aucun écran** n'évoque de dashboard patrimonial, de chat IA ni de base de connaissance.

## Comment s'en servir

- **Navigation** : le rail de gauche, les flèches ← → de la barre du haut, ou les touches clavier ← →.
- **Écrans cliquables** : les boutons principaux enchaînent vraiment (Rechercher → Résultats → Fiche → Contacter → OTP → Confirmation ; côté agence : Mes biens → fiche bien, Mes leads → fiche lead ou achat). Survole : ce qui s'entoure est cliquable.
- **États** : les pastilles sous le titre basculent les 67 états. Pas seulement le cas heureux — vide, chargement, erreur, cas limite.
- **Modes** : `J'investis / J'habite` recompose le vocabulaire et les chiffres (rendement ↔ mensualité) sans perdre les favoris, communs aux deux modes.
- **Responsive** : bascule `Auto / Desktop / Tablette / Mobile` en barre du bas. **Auto** suit la largeur réelle de la fenêtre (< 700 px mobile · < 1080 px tablette).
- **Annotations** : les pastilles ocre renvoient aux décisions UX listées sous chaque écran. Décochable pour une lecture propre en réunion.

## Les règles tactiles (mobile & tablette)

- **Bottom sheets, plus de popins.** Les feuilles de détail s'ancrent en bas, pleine largeur, poignée de préhension, actions au pouce. La tablette suit la même règle.
- **Le CTA « Contacter l'agence » ne quitte jamais l'écran — sans jamais se dédoubler** (`IntersectionObserver`).
- **Le chiffre de la barre sticky ouvre son détail.** Appui sur le score (cible 45 px) → bottom sheet des 4 critères pondérés → analyse complète. Sur un bien non noté, le sheet dit pourquoi au lieu d'inventer une note.
- **Cibles tactiles à 44 px**, champs de saisie à 16 px (en dessous, iOS zoome au focus), safe-areas iOS respectées.
- **Aucun tableau en mobile.** Les tableaux du côté agence ont une vraie liste de cartes — mêmes données, même action.
- **Zéro débordement horizontal**, vérifié sur toutes les combinaisons écran × état × connecté/visiteur.

## Les règles respectées

- **Contenu réel uniquement.** Zéro lorem ipsum, chiffres cohérents entre eux d'un écran à l'autre.
- **Deux biens multi-mandats** (T3 Lyon, Immeuble Roubaix) : avec un seul, la bascule 48 h paraissait anecdotique alors qu'elle est structurelle.
- **Microcopy sous contrainte de vocabulaire** — aucun terme banni (*opportunité*, *coup de cœur*, *rentabilité*, *en un clic*…), « gratuit » jamais employé sans expliquer le modèle.
- **Le cas limite est dans la liste, pas à part** — la 4ᵉ annonce cumule photo absente, DPE G et rendement non calculable. Si un écran tient avec elle, il tient partout.
- **Typographie FR** — espaces insécables avant € % m², virgule décimale, chiffres tabulaires alignés à droite.
- **La nav suit l'état, pas la bascule globale** : les états visiteur affichent « Se connecter / S'inscrire », les états connectés affichent l'avatar.

## Ce qu'on ne fera pas

- **Pas de grille de biens sans critère** — ni « populaires », ni « coups de cœur ».
- **Pas de modale d'onboarding.** Un produit dont l'argument est « on ne vous force à rien » ne commence pas par un écran qu'on ne peut pas fermer.
- **Pas de centre de notifications séparé.** La home *est* le centre de notifications.
- **Jamais deux blocs primaires.**
