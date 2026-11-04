# Application Solina

Application web installable (Mac et iPhone) : accueil du jour, pipeline, prospects, contacts, planning. Aucune donnée dans ce dossier : l'application lit et écrit `prospection/prospects.json` du dépôt privé `maison-solina` via l'API GitHub, avec une clé d'accès personnelle (fine grained, limitée à ce dépôt, Contents en lecture et écriture) que Fanny colle une fois par appareil. La clé reste sur l'appareil et n'est jamais écrite dans le dépôt.

## Publication

Le dossier est publié tel quel sur GitHub Pages depuis un dépôt public séparé, `solina-app`, qui ne contient que ce code. Pour mettre l'application à jour après une modification ici :

    git subtree push --prefix application app main

(le remote `app` pointe vers https://github.com/concinafanny-rgb/solina-app.git). Changer `VERSION` dans `sw.js` à chaque publication pour que les appareils récupèrent la nouvelle version.

## Application Mac

`mac/` contient l'application Mac native (fenêtre WebKit qui embarque ce dossier). Après toute modification de `application/`, relancer `./mac/construire.sh` : elle se réinstalle dans /Applications.
