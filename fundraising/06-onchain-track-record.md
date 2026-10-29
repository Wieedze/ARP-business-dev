# Le track record on chain

Construire sur Intuition donne à ARP un avantage rare avant la levée : la ligne de traction est publique et recalculable. Un investisseur n'a pas à croire tes chiffres, il peut les refaire lui même à partir du graphe.

## Ce que l'investisseur peut vérifier sans toi

| Chiffre | D'où il vient | Comment le recalculer |
| --- | --- | --- |
| Agents distincts qui déclarent | Triples `(agent, uses, tool)` sur Intuition mainnet | Requête sur l'indexeur Intuition, filtrée sur le prédicat `uses` |
| Déclarations par semaine | Horodatage des triples et des positions | Même requête, groupée par semaine |
| Part venant d'adresses hors fondateur | Adresses des déposants | Exclure la liste publiée des adresses ARP |
| Outils couverts | Objets des triples `uses` | Compter les objets distincts |

## Ce qu'il faut publier pour que la ligne soit crédible

1. **La liste de tes propres adresses** (attesteur ARP, agents de test). Un investisseur sait que l'on chain se gonfle ; exclure toi même tes adresses répond à la question avant qu'il la pose.
2. **La requête exacte** qui produit les chiffres, dans ce dépôt ou dans le dépôt ARP, avec la date de chaque exécution.
3. **Un instantané mensuel des résultats,** pour que la courbe existe même si l'indexeur change.
4. **Les agents distincts regroupés par opérateur,** pour qu'un opérateur avec cent agents ne compte pas pour cent.

## Les autres lignes que tu as déjà

1. **Sofia :** une subvention Intuition dans la cohorte 1 (annoncée le 4 février 2026, 100k USDT répartis entre 9 équipes), un historique de commits public.
2. **ARP :** six mois de travail visibles sur GitHub depuis avril 2026, avec un journal de décisions détaillé.
3. **Les mesures publiées :** tes relevés sur ERC-8004 et sur les copies de skills sont des observations originales, datées et reproductibles. Elles montrent la rigueur avant même la traction.

## La phrase pour un investisseur

> Every number in my updates is recomputable from the Intuition graph with the query in the repo. I publish my own addresses so you can exclude them. You don't have to trust my dashboard.

## La limite à reconnaître

Une ligne on chain prouve l'activité, pas la valeur. Elle doit être lue avec les autres signaux : retour des agents dans le temps, éditeurs qui paient le badge, agrégateurs qui demandent la donnée.
