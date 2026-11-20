\# REPONSES – TP 6 : Variables d'environnement, Inputs et Outputs



\## Q1. Pourquoi la variable n'est-elle pas disponible dans la step qui l'a définie ?



La variable enregistrée dans GITHUB\_ENV est disponible uniquement dans les steps suivantes du même job. Elle n'est pas disponible dans la step qui l'a définie, car GitHub Actions applique les modifications d'environnement après la fin de cette step.



\## Q2. Quelle est la portée de GITHUB\_ENV ?



GITHUB\_ENV permet de partager les variables entre les différentes steps d'un même job. Elles ne sont pas automatiquement accessibles dans les autres jobs. Dans le job verify-env, APP\_NAME est donc vide.



\## Q3. Que se passe-t-il si on utilise > au lieu de >> dans GITHUB\_OUTPUT ?



L'opérateur > écrase le contenu précédent du fichier. Si plusieurs outputs sont définis dans la même step, les précédents peuvent être supprimés. L'opérateur >> ajoute les nouvelles valeurs sans effacer les anciennes.



\## Q4. Pourquoi GITHUB\_ENV ne suffit-il pas ici ?



GITHUB\_ENV permet de partager des variables uniquement entre les steps d'un même job. Pour communiquer entre plusieurs jobs, il faut utiliser GITHUB\_OUTPUT, déclarer les outputs du job et utiliser needs pour récupérer les résultats.



\## Q5. Que se passe-t-il si on retire needs: build du job deploy ?



Le job deploy ne dépend plus du job build et peut démarrer en parallèle. Il n'attend donc plus sa fin. De plus, il ne peut plus accéder correctement à ses outputs avec needs.build.outputs.full\_version.

