

\# TP 8 – Stratégies GitHub Actions



\## Q1. Combien de jobs sont générés ? Donnez la liste des combinaisons.



6 jobs sont générés :



\- Ubuntu / Python 3.11

\- Ubuntu / Python 3.12

\- Ubuntu / Python 3.13

\- Windows / Python 3.11

\- Windows / Python 3.12

\- Windows / Python 3.13



\## Q2. Combien de jobs au total ?



6 jobs au total.



La matrice initiale contient 6 combinaisons.

L'exclusion de Windows avec Python 3.11 donne 5 jobs.

L'ajout d'Ubuntu avec Python 3.14 donne 6 jobs.



\## Q3. Que se passerait-il si vous tentiez d'exclure la combinaison 3.14 ? Pourquoi ?



La combinaison Python 3.14 ne serait pas supprimée, car include est appliqué après exclude.

Il faut supprimer cette combinaison directement dans include.



\## Q4. Quelle est la différence observée ? Dans quel cas choisiriez-vous true ? false ?



Avec fail-fast: true, dès qu'un job échoue, les autres jobs en cours ou en attente peuvent être annulés.



Avec fail-fast: false, tous les jobs continuent leur exécution même si certains échouent.



Je choisirais true pour arrêter rapidement les tests en cas d'erreur.

Je choisirais false pour obtenir les résultats de toutes les combinaisons.



\## Q5. Donnez deux raisons d'utiliser max-parallel en entreprise.



1\. Réduire les coûts liés à l'utilisation simultanée de plusieurs runners.

2\. Limiter la consommation des ressources et éviter la surcharge de l'infrastructure.



