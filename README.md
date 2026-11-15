# CO2 Tanks

**[▶ Jouer dans le navigateur](https://ghoster-001.github.io/CO2-Tanks/)**

Jeu de chars en labyrinthe, style arcade rétro. Un seul fichier HTML (hors polices Google Fonts et bibliothèque PeerJS pour le mode en ligne).
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

## Mode en ligne

Le jeu choisit tout seul son transport réseau :

- **Sur GitHub Pages ou en fichier local** : connexion directe entre joueurs en WebRTC, avec la bibliothèque [PeerJS](https://peerjs.com) (chargée depuis unpkg) et son service de signalisation public gratuit. Le premier joueur arrivé dans un salon en devient le relais, les autres s'y connectent. L'hôte calcule toute la partie, les invités envoient leurs touches et affichent ce qu'il leur renvoie.
- **Sur une page publiée dans claude.ai** : le canal temps réel `room` de la page, réservé aux personnes qui ont accès à cette page.

Ces deux mondes sont séparés : un hôte sur GitHub Pages ne peut pas être rejoint depuis claude.ai, et inversement.

Limites du transport WebRTC :
- Le service de signalisation public n'offre aucune garantie de disponibilité.
- Il n'y a pas de serveur TURN : certains réseaux d'entreprise ou connexions mobiles empêchent la connexion directe.
- Le jeu est conçu pour des parties entre amis, pas pour des centaines de joueurs.

Pour utiliser votre propre service de signalisation, définissez `window.CO2_PEER_OPTS` avant le chargement du script, par exemple `{host:'mon-serveur', port:443, path:'/peerjs', secure:true}`.

## Inspiration

D'après AZ Tanks de 1001jeux.fr. Projet indépendant, sans code ni ressources de l'original.
