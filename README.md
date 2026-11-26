# Kadenas · la sonde extérieure

Le contrôle 10 du [socle Kadenas](https://kadenas.fr/socle/) : chaque site
opéré par Seiyar est interrogé **depuis l'extérieur de son serveur**, et Seiyar
est alerté dès qu'il ne répond plus.

- **Quoi** : une page d'accueil par site, en HTTPS. Un code 2xx est une réponse ;
  tout le reste, ou rien au bout de 20 secondes, est un échec.
- **Quand** : toutes les 5 minutes environ. GitHub peut retarder un passage
  quand ses machines sont chargées.
- **Qui** : la liste vient de [kadenas.fr/sites.json](https://kadenas.fr/sites.json),
  la même que celle des [pages de vérification](https://kadenas.fr/). Rien n'est
  recopié ici.
- **Alerte** : un site qui échoue deux fois, à 30 secondes d'écart, fait échouer
  le passage, et GitHub prévient par e-mail.
- **Comment se présente-t-elle** : `Kadenas-Sonde/1.0 (monitor; +https://kadenas.fr/socle/)`.

Le dépôt est public exprès : la sonde fait partie des contrôles publics et datés.
Elle ne lit que des pages publiques, n'a aucun secret et n'écrit rien.

Le passage du jour se lit dans l'onglet [Actions](../../actions).
