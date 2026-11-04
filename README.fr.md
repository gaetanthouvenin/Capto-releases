# Capto

[English](README.md) · **Français**

Capto est un outil de capture d'écran pour Windows 10 et 11 : capturez une zone, une fenêtre ou un écran depuis n'importe quelle application, annotez-la, puis collez-la, enregistrez-la ou retrouvez-la plus tard dans l'historique. Il sait aussi capturer une page entière en la faisant défiler, copier le texte d'une image, et enregistrer l'écran en vidéo, avec le son, que vous pouvez couper, transformer en GIF animé ou transcrire.

- **À une touche de distance.** Les raccourcis fonctionnent depuis n'importe quelle application ; Capto attend dans la zone de notification.
- **Prêt à coller.** Par défaut, chaque capture est dans le presse-papiers dès qu'elle est prise.
- **Rien ne se perd.** Chaque capture et chaque vidéo sont gardées dans un historique avec recherche, annotations comprises.
- **Tout reste sur votre PC.** Pas de compte, pas de cloud, pas de télémétrie. Les seuls accès réseau sont la recherche de mises à jour sur ce dépôt et, si vous utilisez la transcription, le téléchargement unique du modèle de transcription que vous choisissez.

![La fenêtre principale de Capto : les boutons de capture, l'historique et une capture annotée](docs/images/fr/main.png)

Ce dépôt contient les installeurs, les paquets de mise à jour et les notes de version de Capto. Le code source n'est pas public.

## Sommaire

- [Installation](#installation)
- [Prise en main](#prise-en-main)
- [Capturer](#capturer)
- [Capture avec défilement](#capture-avec-défilement)
- [Copier le texte](#copier-le-texte)
- [Enregistrer une vidéo](#enregistrer-une-vidéo)
- [L'historique](#lhistorique)
- [L'éditeur d'annotations](#léditeur-dannotations)
- [Couper une vidéo et exporter un GIF](#couper-une-vidéo-et-exporter-un-gif)
- [Transcrire une vidéo](#transcrire-une-vidéo)
- [Paramètres](#paramètres)
- [Raccourcis clavier](#raccourcis-clavier)
- [Mises à jour](#mises-à-jour)
- [Où sont vos données](#où-sont-vos-données)
- [Désinstallation](#désinstallation)
- [Dépannage](#dépannage)

## Installation

1. Téléchargez `Capto-win-Setup.exe` depuis la [dernière version](https://github.com/gaetanthouvenin/Capto-releases/releases/latest).
2. Lancez-le. L'installeur n'est pas encore signé : Windows SmartScreen signale un « éditeur inconnu ». Cliquez sur **Informations complémentaires**, puis **Exécuter quand même**.
3. Capto s'installe pour l'utilisateur courant uniquement (pas besoin de droits administrateur), dans `%LocalAppData%\CaptoApp`, ajoute un raccourci au menu Démarrer et se lance.

`Capto-win-Portable.zip` est la même application sans installation : décompressez-la où vous voulez et lancez `Capto.exe`.

## Prise en main

Capto ouvre sa fenêtre principale : une barre avec les boutons de capture, l'historique à gauche et la capture sélectionnée à droite. Son icône apparaît aussi dans la zone de notification, près de l'horloge ; un clic droit dessus donne les commandes de capture, les paramètres et **Quitter**.

Le plus rapide :

1. Appuyez sur **Ctrl+Maj+C** depuis n'importe quelle application.
2. Faites glisser la souris sur la partie de l'écran voulue.
3. Collez (**Ctrl+V**) dans votre messagerie, votre e-mail ou votre document.

Fermer la fenêtre principale laisse Capto tourner dans la zone de notification (réglable dans les paramètres) : les raccourcis restent disponibles. Activez **Démarrer avec Windows** dans les paramètres pour que Capto soit prêt à chaque ouverture de session.

## Capturer

| Capture | Raccourci | Ce qu'elle fait |
|---|---|---|
| Zone | Ctrl+Maj+C | Tracez un rectangle sur l'écran. |
| Fenêtre | Ctrl+Maj+W | Survolez une fenêtre et cliquez dessus. |
| Écran | Ctrl+Maj+F | Capture l'écran sous le pointeur de la souris. |
| Tous les écrans | Ctrl+Maj+Alt+F | Capture tous les moniteurs dans une seule image. |
| Répéter la dernière zone | Ctrl+Maj+Alt+C | Capture le même rectangle que la dernière capture de zone, sans le resélectionner. |
| Zone différée | Ctrl+Maj+D | Attend quelques secondes, puis ouvre la sélection de zone. |
| Capture avec défilement (bêta) | aucun par défaut | Fait défiler une zone et l'assemble en une seule image haute (voir [Capture avec défilement](#capture-avec-défilement)). |
| Copier le texte d'une zone | aucun par défaut | Copie le texte d'une zone au lieu d'une image (voir [Copier le texte](#copier-le-texte)). |

Les mêmes commandes sont dans la barre de la fenêtre principale (les moins courantes sous **Autres captures**) et dans le menu de l'icône de la zone de notification. Les deux qui n'ont pas de raccourci peuvent en recevoir un dans **Paramètres › Raccourcis**.

![Le menu Autres captures : capture avec défilement, copier le texte d'une zone, répéter la dernière zone et les captures différées](docs/images/fr/more.png)

### Sélectionner une zone ou une fenêtre

Au lancement d'une capture de zone ou de fenêtre, l'écran se fige : ce que vous sélectionnez est exactement ce qui était affiché au moment du raccourci, même si un menu ou une infobulle se ferme entre-temps.

- **Zone :** faites glisser la souris pour tracer le rectangle ; sa taille en pixels s'affiche à côté.
- **Fenêtre :** survolez une fenêtre pour la mettre en évidence, puis cliquez. **Tab** passe à la fenêtre suivante, pratique pour les fenêtres cachées derrière d'autres. La fenêtre est capturée seule, même là où d'autres fenêtres la recouvrent.
- **W** passe en sélection de fenêtre, **R** revient à la sélection de zone, **S** passe à une [capture avec défilement](#capture-avec-défilement) et **T** à la [copie de texte](#copier-le-texte).
- **Échap** annule.

La barre en haut de l'écran rappelle le mode et les touches ; la taille du rectangle s'affiche à son coin.

<img src="docs/images/fr/overlay-region.png" width="720" alt="Sélection d'une zone : le reste de l'écran est assombri et la taille de la sélection est affichée">

### Formats de zone

La sélection de zone peut suivre un format au lieu d'un rectangle libre :

- **Proportions** (16:9, 4:3, 1:1) : le rectangle garde ses proportions pendant que vous le tracez.
- **Tailles fixes** (1280 × 720, 1920 × 1080, 800 × 600) : un cadre de cette taille suit la souris ; cliquez pour le poser.

Pendant la sélection, **C** fait défiler les formats, **1** à **9** en choisissent un directement et **0** revient à **Libre**. Capto retient le dernier format utilisé. Vous pouvez ajouter jusqu'à 8 formats personnels dans **Paramètres › Formats de zone**.

<img src="docs/images/fr/overlay-ratio.png" width="720" alt="Sélection d'une zone en 16:9 : le format s'affiche à côté de la taille">

### Capture différée

Une capture différée affiche un petit compte à rebours dans un coin de l'écran (3, 5 ou 10 secondes, 5 par défaut ; il n'apparaît jamais dans l'image) avant de capturer, ce qui laisse le temps d'ouvrir un menu ou de survoler un élément. **Échap** annule le compte à rebours. Les entrées différées sont sous **Autres captures** dans la fenêtre principale et sous **Capture différée** dans le menu de l'icône ; le délai se règle dans **Paramètres › Capture**.

### Après une capture

Par défaut, la capture est copiée dans le presse-papiers et ajoutée à l'historique. Selon les paramètres, Capto peut aussi jouer un son, ouvrir l'éditeur, afficher une notification (seulement quand la fenêtre principale est masquée) et dessiner le pointeur de la souris dans l'image.

## Capture avec défilement

Une capture avec défilement saisit une zone plus haute que l'écran, comme une longue page web, un document ou une conversation : Capto la fait défiler et assemble ce qu'il voit en une seule image. Cette fonctionnalité est en bêta : elle ne défile que vers le bas, dans une zone qui tient sur un seul écran.

1. Choisissez **Capture avec défilement (bêta)** sous **Autres captures** ou dans le menu de l'icône, ou appuyez sur **S** pendant une sélection de zone.
2. Faites glisser la souris sur la zone qui défile, de préférence avec sa barre de défilement.
3. Capto fait défiler la zone avec la molette et assemble au fur et à mesure. Un cadre marque la zone et une petite barre affiche la hauteur déjà capturée ; ni l'un ni l'autre n'apparaissent dans l'image.
4. La capture s'arrête seule à la fin du contenu ou à la hauteur maximale (20 000 pixels, moins pour les zones très larges). **Terminer** (ou **Échap**) l'arrête plus tôt en gardant ce qui a été capturé, **Annuler** ne garde rien.

<img src="docs/images/fr/overlay-scrolling.png" width="720" alt="Sélection de la zone à faire défiler : le mode Défilement, la pastille Manuel et la taille de la sélection">

- **Mode manuel :** appuyez sur **M** (ou cliquez sur **Manuel**) avant de tracer la zone pour la faire défiler vous-même, à la molette ou avec la barre de défilement, puis cliquez sur **Terminer**. Faites défiler régulièrement vers le bas : si vous allez trop vite, Capto vous demande de ralentir, et remonter un peu lui permet de retrouver sa place.
- Quand Capto ne peut pas faire défiler la zone (une fenêtre lancée en administrateur, par exemple), il passe en mode manuel et l'indique dans sa barre. Bouger la souris ou appuyer sur une touche pendant le défilement automatique passe aussi la main au mode manuel : continuez à la main, ou cliquez sur **Terminer**.
- Le résultat est une capture ordinaire de l'historique, copiée dans le presse-papiers comme les autres. Les en-têtes qui restent en haut de la page n'apparaissent qu'une fois, et le pointeur de la souris n'est jamais dans l'image. Le recadrage et la découpe, dans l'éditeur, aident à raccourcir une longue image.

## Copier le texte

Capto sait lire le texte d'une image et le copier dans le presse-papiers, prêt à coller comme du texte. C'est Windows qui reconnaît le texte, sur votre PC.

- **Depuis l'écran :** choisissez **Copier le texte d'une zone** sous **Autres captures** ou dans le menu de l'icône, ou appuyez sur **T** pendant une sélection de zone, puis faites glisser la souris sur le texte. Seul le texte est copié : rien n'est ajouté à l'historique.
- **Depuis une capture :** **Copier le texte** dans le menu d'un élément de l'historique (clic droit ou **…**), ou dans l'éditeur. Le texte est lu sur l'image telle que vous la partagez : recadrez d'abord pour n'en copier qu'une partie ; le texte flouté est ignoré et vos annotations de texte sont lues aussi.

Le texte garde une ligne par ligne de l'image, avec une ligne vide entre les paragraphes et les colonnes. La barre d'état indique combien de lignes ont été copiées, ou qu'aucun texte n'a été reconnu.

La reconnaissance utilise les langues de reconnaissance de texte (OCR) installées dans Windows, par défaut les langues d'affichage de Windows. **Langue du texte reconnu**, dans **Paramètres › Capture**, en choisit une autre, par exemple pour lire des captures en anglais sur un Windows en français. Quand aucune langue n'est installée, Capto explique comment en ajouter une : dans **Paramètres Windows › Heure et langue › Langue et région**, ouvrez les options d'une langue et ajoutez **Reconnaissance optique de caractères**. Le texte de droite à gauche et le texte vertical ne sont pas pris en charge.

## Enregistrer une vidéo

Capto enregistre une zone, une fenêtre ou un écran entier dans une vidéo MP4 (H.264), avec le son de l'ordinateur et, si vous le voulez, votre microphone.

1. Appuyez sur **Ctrl+Maj+Alt+R**, cliquez sur **Vidéo** dans la barre de la fenêtre principale, ou choisissez **Enregistrer une vidéo** dans le menu de l'icône.
2. Choisissez quoi enregistrer, comme pour une capture : tracez une zone, cliquez sur une fenêtre, ou appuyez sur **S** et cliquez sur un écran. **W** et **R** passent en sélection de fenêtre et de zone, et les formats de zone fonctionnent aussi.
3. Un compte à rebours de 3 secondes démarre, puis l'enregistrement.
4. Appuyez de nouveau sur **Ctrl+Maj+Alt+R**, ou cliquez sur **Arrêter** dans la barre d'enregistrement : la vidéo est ajoutée à l'historique.

Pendant la sélection, les pastilles en haut de l'écran indiquent les sons qui seront enregistrés : **A** active ou coupe le son système, **M** le microphone, pour cet enregistrement seulement.

Pendant l'enregistrement, une petite barre affiche le temps écoulé, avec **Suspendre** / **Reprendre**, **Arrêter**, un bouton pour abandonner l'enregistrement, et un bouton pour couper chaque source de son avec son vumètre. Déplacez-la par sa poignée. Ni la barre ni le cadre autour de la zone enregistrée n'apparaissent dans la vidéo. Les mêmes commandes sont dans le menu de l'icône.

- Une vidéo de fenêtre suit la fenêtre quand vous la déplacez, mais les menus et les infobulles n'y apparaissent pas : enregistrez une zone pour les montrer.
- L'enregistrement s'arrête seul, en gardant la vidéo, quand il atteint la durée maximale (60 minutes par défaut), quand la fenêtre enregistrée se ferme ou quand le disque est presque plein.
- Si Capto ou Windows s'arrête pendant un enregistrement, la vidéo est récupérée au démarrage suivant.
- L'enregistrement vidéo demande Windows 10 version 2004 ou plus récent. Sur une édition N de Windows, installez d'abord le Media Feature Pack.

## L'historique

Chaque capture et chaque vidéo sont gardées dans l'historique de la fenêtre principale, la plus récente en haut. Sélectionnez une vidéo pour la lire dans le panneau de détail (**Espace** lance et met en pause) ; ses détails indiquent sa durée, sa taille et les sons enregistrés.

- **Rechercher** (**Ctrl+F**) par nom, titre de fenêtre ou date.
- **Copier** (**Ctrl+C**) remet la capture, avec ses annotations, dans le presse-papiers. Pour une vidéo, il copie le fichier, prêt à coller dans un dossier ou une conversation.
- **Copier le texte** copie le texte de la capture (voir [Copier le texte](#copier-le-texte)), ou la transcription d'une vidéo transcrite.
- **Transcrire**, sur une vidéo avec son, transforme sa parole en texte (voir [Transcrire une vidéo](#transcrire-une-vidéo)).
- **Enregistrer** (**Ctrl+S**) l'écrit dans le dossier d'export par défaut, **Enregistrer sous** (**Ctrl+Maj+S**) demande où ; en PNG ou JPEG pour une capture, en MP4 pour une vidéo.
- **Faites glisser** une capture de l'historique vers une autre application (un e-mail, une messagerie, un dossier) pour y déposer l'image.
- **Annoter** (**Entrée**) ouvre l'éditeur.
- **Renommer** (**F2**) donne à la capture un nom que la recherche retrouve.
- **Ouvrir le fichier** et **Afficher dans le dossier** donnent accès au fichier image.
- **Supprimer** (**Suppr**) envoie la capture dans la Corbeille de Windows, d'où elle peut être restaurée. Plusieurs captures peuvent être sélectionnées et supprimées d'un coup.

L'historique peut se nettoyer tout seul : dans **Paramètres › Stockage**, indiquez combien de jours garder les captures et combien en garder au maximum (0 = sans limite). Les plus anciennes partent à la Corbeille. Les vidéos ont leur propre limite, une taille totale réglée dans **Paramètres › Enregistrement** (20 Go par défaut).

## L'éditeur d'annotations

Ouvrez-le avec **Annoter** (ou **Entrée**) sur une capture, ou automatiquement après chaque capture en activant **Ouvrir l'éditeur après la capture**.

![L'éditeur d'annotations : les outils à gauche, les propriétés de l'outil flèche en haut, une capture avec un surlignage, un cadre, une flèche, un texte et deux pastilles numérotées](docs/images/fr/editor.png)

| Outil | Touche | Usage |
|---|---|---|
| Sélection | V | Sélectionner, déplacer, redimensionner, dupliquer (Ctrl+D) ou supprimer (Suppr) une annotation. |
| Flèche | A | Pointer quelque chose. |
| Rectangle | R | Encadrer une zone, avec ou sans remplissage. |
| Texte | T | Écrire une note, éventuellement dans un cadre qui reste lisible sur une image chargée. |
| Numéro | N | Poser des pastilles numérotées (1, 2, 3…) pour des instructions pas à pas ; en supprimer une renumérote les autres. |
| Surligneur | H | Surligner du texte comme au feutre. |
| Flou | B | Masquer un mot de passe, un nom ou un e-mail en pixelisant ou en floutant une zone. |
| Recadrer | C | Ne garder qu'une partie de l'image. |
| Découpe | X | Retirer une bande horizontale ou verticale et recoller les deux bords (droit, zigzag ou déchiré), par exemple pour raccourcir une longue page. |

- La couleur, l'épaisseur et la taille sont dans la barre de propriétés de l'outil choisi. Maintenez **Maj** en dessinant pour contraindre la forme (flèches droites, carrés).
- **Ctrl+Z** / **Ctrl+Y** annulent et rétablissent, **Ctrl+S** enregistre les annotations, **Ctrl+C** copie l'image annotée, **Ctrl+Entrée** enregistre, copie et ferme l'éditeur. **Copier le texte** copie le texte de l'image annotée.
- Zoomez avec **Ctrl+-** / **Ctrl++**, **Ctrl+0** ajuste l'image à la fenêtre, **Ctrl+1** l'affiche en taille réelle.
- Les annotations restent modifiables : l'image d'origine n'est jamais modifiée, et le recadrage comme la découpe peuvent être annulés à tout moment. Les copies, les fichiers enregistrés et les glisser-déposer contiennent toujours l'image annotée, avec le flou appliqué définitivement.

## Couper une vidéo et exporter un GIF

Sélectionnez une vidéo dans l'historique, puis cliquez sur **Couper** pour n'en garder qu'une partie. Une frise d'images montre la vidéo, avec une poignée pour le début et une pour la fin de l'extrait.

<img src="docs/images/fr/trim.png" width="720" alt="Le mode coupe : la vidéo, la frise d'images avec l'extrait choisi encadré en orange, le début, la fin et la durée de l'extrait">

- Faites glisser les poignées, ou avancez image par image avec **←** / **→** (**Maj** saute d'une seconde) et placez le début et la fin sur l'image courante avec **I** / **O**. **Origine** / **Fin** vont au début et à la fin.
- **Espace** lit l'extrait. En pause, l'image affichée est exactement celle où passera la coupe.
- **Couper** (**Entrée**) crée l'extrait comme un nouvel élément de l'historique, coupé à l'image près, avec son son. L'original reste intact, sauf si vous cochez **Mettre l'original à la Corbeille**.
- **Exporter en MP4…** demande où enregistrer l'extrait dans un fichier, sans l'ajouter à l'historique. **Échap** quitte sans couper.

**Exporter en GIF**, sur une vidéo ou depuis le mode coupe pour l'extrait choisi, crée un GIF animé : 10, 15 ou 20 images par seconde (15 par défaut), une largeur de 640, 800 (par défaut) ou 1280 pixels ou la taille originale, une palette par image ou globale, la lecture en boucle et le tramage. La taille estimée se met à jour quand vous changez les options. **Copier aussi le fichier** met le GIF dans le presse-papiers, pour le coller dans Teams, Slack ou Outlook. **Exporter** l'écrit dans le dossier d'export par défaut, **Enregistrer sous…** demande où. Un GIF dure au plus 60 secondes : pour une vidéo plus longue, Capto ouvre le mode coupe sur sa première minute pour que vous choisissiez l'extrait.

<img src="docs/images/fr/gif-export.png" width="460" alt="La fenêtre Exporter en GIF : images par seconde, largeur, palette, boucle, tramage, copie du fichier et taille estimée">

## Transcrire une vidéo

Capto sait transformer la parole d'une vidéo en texte et en sous-titres. La transcription tourne sur votre PC avec le modèle de reconnaissance vocale Whisper : le son de vos vidéos ne quitte jamais votre ordinateur.

1. Une fois pour toutes, dans **Paramètres › Transcription**, choisissez un modèle de transcription, cliquez sur **Télécharger**, puis sur **Enregistrer**. Le modèle n'est téléchargé qu'une fois, depuis huggingface.co. **Small** (465 Mo) est recommandé et choisi par défaut ; **Tiny** (74 Mo) est très rapide mais approximatif, **Medium** et **Large v3 Turbo** (1,4 et 1,5 Go) sont plus précis mais lents et demandent beaucoup de mémoire.
2. Sélectionnez une vidéo avec son et cliquez sur **Transcrire**, dans le panneau de transcription sous le lecteur ou dans le menu de la vidéo. Pour que chaque nouvelle vidéo soit transcrite après son enregistrement, activez **Transcrire automatiquement les nouveaux enregistrements avec son** dans les mêmes paramètres.
3. La transcription tourne en arrière-plan, une vidéo à la fois, et attend pendant un enregistrement. Le panneau affiche sa progression, avec **Annuler**. Quand la fenêtre principale est masquée, une notification prévient quand elle est terminée.

<img src="docs/images/fr/transcript.png" width="720" alt="Une vidéo avec sa transcription sous le lecteur : la langue, les liens Copier, Enregistrer les sous-titres et Transcrire à nouveau, et le moment de chaque phrase">

Le panneau de transcription liste les phrases avec leur moment dans la vidéo : cliquez sur l'une d'elles (ou appuyez sur **Entrée**) pour y aller. **Copier** met tout le texte dans le presse-papiers, comme **Copier le texte** dans le menu de la vidéo. **Enregistrer les sous-titres…** écrit un fichier SubRip (`.srt`), que les lecteurs et éditeurs vidéo savent ouvrir. **Transcrire à nouveau** refait la transcription, par exemple après un changement de modèle ou de langue.

- La langue parlée est détectée automatiquement ; si la détection se trompe, choisissez la langue dans **Paramètres › Transcription**.
- Plus le modèle est gros, plus la transcription est lente : commencez par **Small** et ne changez qu'en cas de besoin.
- Un extrait créé avec **Couper** n'a pas de transcription : transcrivez-le à part. Une vidéo sans son ne peut pas être transcrite.

## Paramètres

Ouvrez-les avec **Ctrl+,** dans la fenêtre principale ou depuis le menu de l'icône. Les changements s'appliquent quand vous cliquez sur **Enregistrer**.

### Général

Démarrer avec Windows, démarrer réduit, fermer dans la zone de notification, notification après une capture, recherche des mises à jour, thème (système, clair ou sombre) et langue. Capto suit la langue de Windows par défaut et existe en français, anglais, allemand, espagnol, italien, portugais, néerlandais, chinois, japonais et coréen ; un changement de langue s'applique au prochain démarrage.

<img src="docs/images/fr/settings-general.png" width="620" alt="Paramètres généraux">

### Capture

Copier dans le presse-papiers, copier aussi le fichier (pratique pour les pièces jointes Outlook), ouvrir l'éditeur après la capture, jouer un son, inclure le curseur, délai des captures différées, et le moteur de capture : Capto utilise Windows Graphics Capture, qui capture aussi les fenêtres masquées ; **Utiliser le moteur de capture GDI** revient à l'ancien moteur, à essayer si des captures sont noires ou incomplètes. **À propos de Capto** indique le moteur utilisé. **Langue du texte reconnu** est la langue que lit **Copier le texte** (par défaut, les langues de Windows).

<img src="docs/images/fr/settings-capture.png" width="620" alt="Paramètres de capture">

### Formats de zone

Les formats intégrés, avec la touche chiffrée qui choisit chacun pendant une sélection, et jusqu'à 8 proportions ou tailles fixes personnelles.

<img src="docs/images/fr/settings-formats.png" width="620" alt="Paramètres des formats de zone">

### Enregistrement

Images par seconde (15, 30 ou 60 ; 30 par défaut), qualité (basse, standard ou haute), inclure le curseur, mettre en évidence les clics par un anneau jaune, compte à rebours de 3 secondes, durée maximale (60 minutes par défaut), taille maximale totale des vidéos (20 Go par défaut ; au-delà, les plus anciennes partent à la Corbeille) et dossier des vidéos. La page indique aussi si un encodeur matériel (GPU) est disponible ; sans lui, l'encodage logiciel peut manquer des images en haute résolution.

**Son :** le son système (ce que joue l'ordinateur) est enregistré par défaut ; le microphone est désactivé par défaut et n'est ouvert que pendant un enregistrement. Choisissez les périphériques de sortie et d'entrée (celui de Windows par défaut, sauf si vous en choisissez un) et le gain de chaque source. Avec des haut-parleurs, le micro capte aussi le son système : préférez un casque.

<img src="docs/images/fr/settings-recording.png" width="620" alt="Paramètres d'enregistrement">

### Transcription

Le modèle de transcription (Small par défaut), avec **Télécharger** et **Supprimer** et un lien vers le dossier des modèles ; la langue parlée (détectée automatiquement par défaut) ; et la transcription automatique des nouveaux enregistrements avec son (désactivée par défaut, disponible une fois le modèle choisi installé). Le téléchargement démarre dès le clic sur **Télécharger** ; fermer les paramètres pendant un téléchargement l'arrête. Le modèle choisi est utilisé une fois que vous avez cliqué sur **Enregistrer**.

<img src="docs/images/fr/settings-transcription.png" width="620" alt="Paramètres de transcription">

### Stockage

Dossier de l'historique, durée de conservation, dossier d'export par défaut, modèle de nom de fichier, format (PNG ou JPEG) et qualité JPEG. Le modèle de nom accepte `{date}`, `{time}`, `{kind}`, `{width}`, `{height}` et `{index}` ; par défaut, `Capto_{date}_{time}`.

<img src="docs/images/fr/settings-storage.png" width="620" alt="Paramètres de stockage">

### Raccourcis

Cliquez sur un raccourci, puis appuyez sur la nouvelle combinaison ; **Retour arrière** efface les raccourcis facultatifs (zone différée, répéter la dernière zone, capture avec défilement, copier le texte d'une zone, suspendre un enregistrement).

<img src="docs/images/fr/settings-hotkeys.png" width="620" alt="Paramètres des raccourcis">

## Raccourcis clavier

**Depuis n'importe quelle application** (modifiables dans les paramètres ; **Suspendre les raccourcis**, dans le menu de l'icône, les coupe temporairement, par exemple quand une autre application a besoin des mêmes touches) :

| Raccourci | Action |
|---|---|
| Ctrl+Maj+C | Capturer une zone |
| Ctrl+Maj+W | Capturer une fenêtre |
| Ctrl+Maj+F | Capturer l'écran sous le pointeur |
| Ctrl+Maj+Alt+F | Capturer tous les écrans |
| Ctrl+Maj+Alt+C | Répéter la dernière zone |
| Ctrl+Maj+D | Capture de zone différée |
| (aucun par défaut) | Capture avec défilement |
| (aucun par défaut) | Copier le texte d'une zone |
| Ctrl+Maj+Alt+R | Démarrer ou arrêter un enregistrement |
| (aucun par défaut) | Suspendre ou reprendre un enregistrement |

**Pendant une sélection :** Échap annule, W / R passent de la fenêtre à la zone, Tab passe à la fenêtre suivante, C change de format de zone, 0 à 9 choisissent un format. Pour une capture, aussi S pour une capture avec défilement (puis M pour le défilement manuel) et T pour copier le texte. Pour une vidéo, S pour un écran entier, A pour le son système et M pour le microphone.

**Pendant une capture avec défilement :** Échap termine en gardant ce qui a été capturé.

**Dans la fenêtre principale :** Ctrl+F rechercher, Ctrl+C copier, Ctrl+S enregistrer, Ctrl+Maj+S enregistrer sous, Entrée annoter, F2 renommer, Suppr supprimer, Ctrl+, paramètres. Sur une vidéo, Espace lance et met en pause ; dans sa transcription, Entrée sur une phrase y amène la vidéo.

**Dans l'éditeur :** V A R T N H B C X pour les outils, Ctrl+Z annuler, Ctrl+Y rétablir, Ctrl+S enregistrer, Ctrl+C copier, Ctrl+Entrée copier et fermer, Ctrl+D dupliquer, Suppr supprimer, Ctrl+0 ajuster, Ctrl+1 taille réelle.

**Pour couper une vidéo :** ← / → une image (Maj : une seconde), I / O placent le début / la fin, Origine / Fin vont au début / à la fin, Espace lit l'extrait, Entrée coupe, Échap quitte.

## Mises à jour

La version installée vérifie ce dépôt au démarrage, puis une fois par jour (désactivable dans **Paramètres › Général**). Quand une nouvelle version est disponible, **Mettre à jour vers x.y.z** apparaît dans le menu de l'icône de la zone de notification : cliquez dessus, Capto télécharge la mise à jour et redémarre. Seules les versions stables sont proposées, jamais les préversions. **À propos de Capto**, dans le même menu, affiche la version installée.

Les changements de chaque version sont listés dans ses [notes de version](https://github.com/gaetanthouvenin/Capto-releases/releases).

## Où sont vos données

| Quoi | Où |
|---|---|
| Captures et annotations | `%LocalAppData%\Capto\captures` (modifiable dans **Paramètres › Stockage**) |
| Vidéos | le dossier `recordings` dans le dossier des captures |
| Transcriptions | un fichier `.srt` à côté de chaque vidéo transcrite, dans le dossier `recordings` |
| Modèles de transcription | `%LocalAppData%\Capto\models\whisper` |
| Paramètres | `%AppData%\Capto\settings.json` |
| Dernière zone et autres états propres à ce PC | `%LocalAppData%\Capto\state.json` |
| Images enregistrées et exportées | `Images\Capto` par défaut |
| L'application elle-même | `%LocalAppData%\CaptoApp` |

## Désinstallation

Désinstallez Capto depuis **Paramètres Windows › Applications › Applications installées**. Les modèles de transcription sont supprimés avec l'application. Vos captures et vos paramètres sont conservés, une réinstallation les retrouve ; supprimez les dossiers `%LocalAppData%\Capto` et `%AppData%\Capto` pour les effacer aussi.

## Dépannage

- **Un raccourci ne fait rien :** une autre application l'utilise déjà, et Capto le signale dans sa barre d'état au démarrage. Choisissez une autre combinaison dans **Paramètres › Raccourcis**.
- **La capture n'est pas dans le presse-papiers :** vérifiez **Copier dans le presse-papiers** dans **Paramètres › Capture** ; la capture est de toute façon dans l'historique.
- **Word insère un lien au lieu de l'image :** désactivez **Copier aussi le fichier** dans **Paramètres › Capture**.
- **Une capture est noire ou incomplète :** activez **Utiliser le moteur de capture GDI** dans **Paramètres › Capture**.
- **Aucun encodeur vidéo H.264 n'est disponible :** sur une édition N de Windows, installez le Media Feature Pack depuis **Paramètres Windows › Applications › Fonctionnalités facultatives**.
- **Windows bloque le microphone :** autorisez les applications de bureau à utiliser le microphone dans **Paramètres Windows › Confidentialité et sécurité › Microphone** ; Capto propose d'ouvrir cette page, ou d'enregistrer sans le microphone.
- **Le micro sonne comme un appel téléphonique :** un casque Bluetooth passe en qualité téléphone quand son micro est utilisé ; prenez un micro filaire ou enregistrez sans.
- **Une capture avec défilement ne défile pas :** la fenêtre est lancée en administrateur ou ignore la molette. Capto passe alors en mode manuel : faites défiler la zone vous-même, puis cliquez sur **Terminer**.
- **Copier le texte indique qu'aucune langue n'est installée :** ajoutez la fonctionnalité **Reconnaissance optique de caractères** à une langue dans **Paramètres Windows › Heure et langue › Langue et région**. Sous Windows 10, ou dans certaines organisations, un administrateur peut être nécessaire.
- **Aucun texte n'est reconnu :** le texte est trop petit (moins d'environ 11 pixels de haut) ou flou. Capturez-le plus grand, par exemple après avoir zoomé dans l'application.
- **Le modèle de transcription ne se télécharge pas :** vérifiez que huggingface.co est accessible (proxy, pare-feu). Capto utilise les paramètres de proxy de Windows.
- **La transcription échoue avec un grand modèle :** le PC manque de mémoire pour lui ; choisissez un modèle plus petit dans **Paramètres › Transcription**.

---

Les versions sont publiées automatiquement par le workflow de release du dépôt source. Ce README, sa traduction et leurs images sont les seuls fichiers maintenus à la main.
