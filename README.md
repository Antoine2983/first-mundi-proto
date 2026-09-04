# Prototype MVP — parcours complet

Prototype cliquable d'une plateforme immobilière. **Un seul fichier, aucune dépendance, fonctionne hors ligne** : ouvre `index.html` dans un navigateur (double-clic).

**26 écrans · 88 états**, vérifiés sur 352 rendus (écran × état × connecté/visiteur × desktop/mobile). On valide ici les **parcours, la hiérarchie de l'information et les états**.

> **💳 Crédits & équipe (09/2026).** Le déblocage d'un acquéreur se paie en **crédits** (20 / 30 / 40), achetés par packs (150 / 400 / 1000), sans expiration ; 40 crédits offerts à l'inscription. Les crédits appartiennent à l'agence, mais **chaque débit du registre dit qui et quand** (auteur + heure, filtrable par agent), le profil montre **les résultats de chaque agent** à côté de ce qu'il a consommé (débloqués · joints · RDV · mandats · leads reçus traités · délai de rappel), et l'administrateur fixe **un plafond mensuel de crédits par agent** — un droit de tirage sur le solde commun, remis à zéro le 1ᵉʳ, jamais un solde à part. Un agent au plafond voit la liste entière et demande une rallonge d'un clic.

> **⚠️ Modèle de leads v2 (brief 08/2026).** L'ancien modèle « contact gratuit mais infos bloquées, qualification à débloquer » est retiré partout. Le nouveau : **tout contact reçu est gratuit, en entier, à vie** — et ce qui se vend est un **acheteur qui n'a pas contacté** (catalogue d'acheteurs anonymisés, 20/30/40 €, identité révélée après achat).

## Ce que contient le prototype

| Groupe | Écrans |
|---|---|
| **Parcours acquéreur** (10) | Accueil ⭐ · Recherche & résultats · Fiche bien ⭐ · Page agence · Mise en relation 1 & 2 · Vérification SMS · Favoris · Mes recherches (enregistrées & récentes) · Paramètres |
| **Estimation & IA** (2) | Estimation + score + avis (bascule investisseur / acquéreur) · Complétude du profil acquéreur |
| **Côté agence** (6) | Choix du profil · Vérification SIRET · Tableau de bord · Mes biens · Fiche bien côté agence · Dépôt d'un bien (4 étapes) |
| **Leads & facturation** (6) | Mes leads (tout gratuit) · Fiche lead · Catalogue d'acheteurs (3 portes : annonce · catalogue+panier · alertes) · Acheter un acheteur · Paiements & factures · Déclaration de vente |
| **Site vitrine** (1) | Landing publique + waitlist |

## Les écrans qui portent le produit

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

### La recherche — localisation, historique, filtres

**« Où » n'est pas un champ, c'est un écran.** Un lieu est un objet typé — commune, arrondissement, quartier, département — avec un parent et un stock de biens. Les zones **se cumulent** et chacune porte **son propre rayon** (`Lyon 7ᵉ + 5 km` et `Villeurbanne seule` coexistent).

- **L'effet d'un rayon est annoncé avant d'être appliqué** : « +5 km inclut Lyon 3ᵉ, Lyon 8ᵉ, Villeurbanne — 1 527 biens au lieu de 412 ».
- **Le chevauchement est dit, pas corrigé en silence.** Les biens sont comptés une seule fois, et l'écran l'explique. Corriger en douce ferait douter de tous les chiffres.
- **La couverture est annoncée** : trois biens sur une commune, on l'écrit — « ce n'est pas votre budget qui est en cause, c'est nous » — avec une alerte de couverture.
- **Pas de dessin sur carte, et on le dit** plutôt que de laisser chercher un bouton absent.

**La barre de la home porte la recherche entière.** C'est la seule surface de recherche d'un visiteur qui arrive à froid — la pilule de nav n'existe que sur les écrans intérieurs. Elle porte donc les deux modes (`⌕ Critères` et `✦ Décrire`, ce dernier était jusqu'ici invisible en première visite), le même écran de zones que partout ailleurs, et — sous la barre, au même emplacement — **des raccourcis pour les froids, l'historique pour ceux qui reviennent**. Contenu opposé, place identique : la barre ne bouge jamais.

**L'historique, c'est deux objets — jamais un.** Les **récentes** s'écrivent toutes seules, ne sont jamais nommées, expirent à 30 jours et ne quittent pas l'appareil sans compte. Les **enregistrées** sont nommées, synchronisées, alertées. **L'étoile est la seule frontière**, au même endroit dans les deux listes : les mélanger obligerait l'utilisateur à ranger une liste qu'il n'a jamais demandée. Quatre points d'entrée — le ↺ de la nav, la tête de la popup de recherche, l'état sans critère, et l'écran « Mes recherches » à deux onglets.

**Les critères actifs se retirent là où ils sont lus.** Chaque critère est une pastille avec sa croix, en haut de la liste. Un utilisateur qui doit rouvrir une popup pour enlever un filtre ne l'enlève pas : il abandonne. La ligne du haut retire, celle du bas ajoute, et un critère actif ne réapparaît jamais dans les suggestions.

**Zéro résultat : on chiffre chaque renoncement** — « +18 biens si vous étendez à 10 km », « +4 si vous acceptez un DPE E ». L'utilisateur choisit ce qui lui coûte le moins au lieu de tout relâcher.

**Aucun filtre ne masque un bien faute de donnée.** Un équipement non déclaré n'est pas un équipement absent ; filtrer dessus retire les biens dont on ne sait rien, et l'écran le dit.

### La fiche bien ne désigne aucune agence

La colonne de droite ne porte que le bien : son prix, son analyse, le bouton. **Aucune agence n'y est « le contact »** — un bien à trois mandats a trois contacts possibles, et en mettre un en avant reviendrait à arbitrer entre des agences dont nous sommes le partenaire, pas l'arbitre. Elles vivent dans le détail du prix, à égalité, chacune avec le sien.

Le chiffre en tête est le prix — celui de l'agence la moins chère, le seul réellement obtenable. Mais **la colonne ne le commente pas** : ni « le plus bas des trois », ni la fourchette. Elle annonce un prix comme n'importe quelle fiche, et c'est le détail qui explique d'où il sort, agence par agence. Jamais de moyenne : ce serait inventer un prix qui n'existe chez personne.

Le **budget total frais de notaire inclus** vit lui aussi dans le détail. Mis en colonne, il transforme un chiffre de décision en accroche et fait douter du prix affiché juste au-dessus.

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
- **Mes leads — tout est là, gratuitement.** Aucune ligne ne porte de prix : identité, téléphone vérifié, email, message, projet arrivent **en entier avec le contact**. L'ancien « à débloquer » n'existe plus nulle part — une agence qui cherche le piège doit pouvoir scroller tout l'écran sans trouver un euro à payer sur ses contacts.
- **Ce qui se vend : des acheteurs invisibles.** Le catalogue propose des acquéreurs inscrits, en recherche active, consentants, **qui n'ont contacté personne**. Règle d'or avant/après achat — visible : critères, commune (jamais l'adresse), projet, score de sérieux, financement oui/non, activité, agences l'ayant acheté ; révélé après paiement : nom, téléphone, email, message. L'onglet Acheteurs s'ouvre sur le **portefeuille entier** — tous les acheteurs de toutes les annonces, groupés par bien, les plus demandés d'abord, comptes qui bouclent (12+7+5+3+2 = 29). Autres portes : « N acheteurs correspondent à ce bien » depuis l'annonce, la recherche libre avec panier (10 pour 150 €) pour prospecter au-delà des mandats, les alertes (achat en 1 clic). Garanties sur l'écran d'achat, pas en CGU : remboursé si injoignable · premier offert · jamais refacturé · fraîcheur honnête. **Une fois acheté, l'acheteur devient un lead** : il rejoint « Mes leads » (mêmes statuts, même fiche, provenance et prix affichés comme faits passés) et sort du catalogue de l'agence — le registre « jamais refacturé », c'est la liste de leads elle-même.
- **L'argument mandat est affiché** : « j'ai déjà 8 acheteurs qualifiés pour votre bien » gagne le rendez-vous vendeur — c'est ce qui justifie le prix au-delà du lead.
- **Le consentement B2C conditionne tout le modèle.** Case séparée de l'envoi de la demande, jamais pré-cochée, révocable depuis les paramètres (effet dans l'heure). Le message côté acquéreur est un bénéfice réel : « des propositions correspondant à ta recherche, y compris off-market, avant publication ». Maquetté à trois endroits : mise en relation étape 2, complétude du profil, paramètres.
- **Le lead sans réponse à 48 h est signalé à l'agence avant de l'être à l'acquéreur.** Le cacher serait déloyal ; le dire en fait le rappel le plus efficace du produit. « Nouveau » côté agence est exactement « Envoyée » côté acquéreur.
- **Un lead partagé le dit, même gratuit.** L'acquéreur adresse sa demande à tous les mandataires du bien : plusieurs agences reçoivent le même contact. Maintenant que rien ne se paie, le dire ne protège plus un prix — ça change la façon de rappeler. « Partagé · N agences » dans la liste et la fiche ; un lead non partagé porte la mention inverse, « Vous seul ».

## La règle des deux sources

**Aucune maquette n'affiche une donnée qui n'a pas de source dans le périmètre acté** : les champs du bien (type, prix, surface, pièces, localisation géocodée, DPE, photos, date de publication) et les mutations notariales publiques (DVF) pour l'estimation.

Écartés : écoles, secteur scolaire, transports, commerces, temps de trajet. Toute donnée exigeant une nouvelle ingestion reste dehors, y compris quand elle serait utile.

Trois limites matérialisées : la **carte de la fiche est statique** (recherche cartographique hors périmètre) · le bloc **« Le quartier »** ne dit que ce que les ventes publiques disent · **aucun écran** n'évoque de dashboard patrimonial, de chat IA ni de base de connaissance.

## Comment s'en servir

- **Navigation** : le rail de gauche, les flèches ← → de la barre du haut, ou les touches clavier ← →.
- **Écrans cliquables** : les boutons principaux enchaînent vraiment (Rechercher → Résultats → Fiche → Contacter → OTP → Confirmation ; côté agence : Mes biens → fiche bien, Mes leads → fiche lead ou achat). Survole : ce qui s'entoure est cliquable.
- **États** : les pastilles sous le titre basculent les 69 états. Pas seulement le cas heureux — vide, chargement, erreur, cas limite.
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
