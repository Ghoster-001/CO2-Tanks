# CO2 Tanks

Jeu de chars en labyrinthe, style arcade rétro. Un seul fichier HTML, sans dépendance (hors polices Google Fonts).
Le dernier char en vie gagne la manche ; les balles rebondissent sur les murs.

## Modes

**Hors ligne**
- **Deux joueurs** : même clavier, grille Petit à Grand, couleur au choix.
- **Contre des bots** : toi contre 1 à 9 bots, grille jusqu'à Très grand.
- **Bots contre bots** : 2 à 10 bots, pour regarder.

**En ligne** (voir la remarque plus bas)
- **Adversaire aléatoire** : appariement automatique, grille tirée au sort.
- **Héberger** : code à 4 caractères, 2 à 10 joueurs, grille jusqu'à Géant (36×24).
- **Rejoindre** : saisir le code de l'hôte.

Les chars apparaissent toujours le plus loin possible les uns des autres.
Sur les grandes cartes, la caméra suit ton char et une mini-carte s'affiche.

## Commandes

| | Avancer | Reculer | Tourner | Tirer |
|---|---|---|---|---|
| Joueur 1 | E | D | S / F | Q |
| Joueur 2 | ↑ | ↓ | ← / → | M |

Les touches suivent la lettre tapée (AZERTY ou QWERTY). Entrée : nouvelle manche. Échap : retour au menu.

## Lancer

Ouvrir `index.html` dans un navigateur, ou activer GitHub Pages sur la branche `main`.

## Remarque sur le mode en ligne

Le mode en ligne utilise la capacité `room` des pages publiées sur claude.ai (`window.claude.use("room")`).
Hors de cette plateforme, par exemple sur GitHub Pages, cette capacité n'existe pas : les boutons en ligne restent grisés et tous les modes hors ligne fonctionnent normalement.
Pour jouer en ligne ailleurs, il faut remplacer la couche réseau (fonctions `hostPre`, `hostSend`, `guestStep`, `startQueue`) par un autre transport, par exemple WebSocket ou WebRTC.

## Inspiration

D'après AZ Tanks de 1001jeux.fr. Projet indépendant, sans code ni ressources de l'original.
