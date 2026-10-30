# ARP : kit de présentation

30 octobre 2026. Copie versionnée du document Claude « ARP : kit de présentation ».

## Vision, mission et but final

Tout le reste découle de ces trois phrases. Elles servent de référence : si un texte sur ARP les contredit, c'est le texte qu'il faut corriger.

| | Français | Anglais (marque) |
| --- | --- | --- |
| **Vision** | Un monde où l'argent suit l'usage : les outils dont les agents dépendent vraiment sont visibles et payés. | *Money follows usage.* |
| **Mission** | Tenir un registre public et ouvert de ce que les agents utilisent vraiment, et si ça marche. | *Keep an open record of what agents actually use, and whether it works.* |
| **But final** | Faire circuler l'argent vers les outils que les agents utilisent vraiment. | *ARP makes money flow to the tools agents actually use.* |
| **Signature** | Les étoiles montrent qui a regardé. ARP montre qui s'en est servi. | *Stars show who looked. ARP shows who used it.* |

**Ce qu'ARP vend** (ADR `0075`) : la place dans la réponse. Un agent nomme un besoin, reçoit une liste ordonnée, et cette place vient de ce que **les autres** ont mis derrière un outil, pas de ses propres dépôts.

**Comment l'argent circule** (ADR `0076`) : ARP prépare les paiements d'un agent vers les outils qu'il a utilisés, l'agent les signe. ARP ne détient jamais l'argent.

**Le rôle d'ARP** (ADR `0094`) : l'annuaire et le vérificateur, jamais le relais. Aucune requête ni aucun prompt ne passe par ARP.

**Les trois principes à répéter**

1. **ARP ne note personne.** Il montre ce que d'autres ont mis derrière un outil, et si l'outil répond.
2. **ARP ne détient rien.** Ni clé, ni argent, ni données : débranche ARP, tout reste sur le graphe.
3. **Chaque chiffre se vérifie.** Toute affirmation publique est livrée avec la commande qui la refait (ADR `0081`).

## Les pitchs

Quatre longueurs, toujours dans le même ordre : un problème, un chiffre, ce que fait ARP, le but. Les versions anglaises servent pour la marque, les investisseurs et les communautés ; la version française sert pour Bpifrance et les événements en France.

**Une phrase**

> ARP makes money flow to the tools agents actually use.

**10 secondes**

> Half the tools AI agents can call don't work, and nobody can tell which. ARP records what agents actually use, and whether it worked, so agents pick tools that work and money flows to them.

**30 secondes**

> There are 48,000 MCP servers and 1.5 million registered agents, and nobody can tell which tools agents actually use. Stars and installs show who looked; reviews are mostly fake accounts.
>
> ARP records each tool call that works, by the agent that made it, on an open graph anyone can read. Developers get a free view that tells them whether a broken tool is their problem or everyone's. Every install adds to a public usage record.
>
> Stars show who looked. ARP shows who used it, so agents pick tools that work, and money flows to the tools agents actually depend on.

**30 secondes, en français**

> Il existe 48 000 serveurs MCP et 1,5 million d'agents enregistrés, et personne ne sait quels outils les agents utilisent vraiment. Les étoiles et les installations montrent qui a regardé ; les avis viennent surtout de faux comptes.
>
> ARP enregistre chaque appel d'outil qui marche, par l'agent qui l'a fait, sur un graphe ouvert que tout le monde peut lire. Les développeurs ont une vue gratuite qui leur dit si un outil en panne l'est chez eux ou chez tout le monde.
>
> Le but : faire circuler l'argent vers les outils que les agents utilisent vraiment.

**2 minutes** (l'ordre du deck)

1. **Le problème.** 84 819 outils recensés, environ la moitié des serveurs MCP ne répondent pas, et les avis ERC-8004 affichent 95 sur 100 en moyenne : ils ne distinguent plus rien.
2. **Pourquoi ça dure.** Tous les signaux actuels se fabriquent gratuitement : fausses étoiles, copies qui battent l'original en installs, avis de comptes sybil.
3. **L'idée.** L'usage est le seul signal qu'un outil ne peut pas produire seul : il faut qu'un autre agent l'appelle, et que ça marche.
4. **Le produit.** Une commande d'installation, un hook dans le runtime de l'agent, et `arp status` qui répond à « c'est moi, ou c'est cassé pour tout le monde ? ». La déclaration publique est un effet secondaire. Le cœur est déjà construit sur testnet.
5. **Pourquoi maintenant.** 40 fois plus de serveurs MCP en un an, des agents qui paient déjà leurs outils via x402, et une norme qui laisse volontairement la couche de confiance aux autres.
6. **L'argent.** Les agents paient pour consulter ARP, en USDC via x402 ; les outils ne paient jamais, donc personne n'achète sa place. ARP finance les dépôts qui apportent une preuve. Au bout, une part des revenus des agents reversée aux outils utilisés.
7. **La suite.** Cent agents que je ne contrôle pas avant EthCC, en avril 2027, et chaque chiffre recalculable depuis le graphe.

## Le vocabulaire

Les mots d'ARP suivent la règle du dépôt (`docs/01`) : ne jamais promettre ce que le protocole ne prouve pas.

| À éviter | Pourquoi | À dire à la place |
| --- | --- | --- |
| *best*, meilleur | ARP ne classe pas la qualité (ADR `0046`) | *most used*, *used by N operators* |
| *score*, note | ARP ne compose aucune note | *what others put behind it*, *success rate reported by N agents* |
| *verified* à propos d'un usage | Seule la joignabilité se vérifie | *declared*, *recorded*, *answers* (pour la joignabilité), *measured by ARP* (pour la sonde) |
| *proof*, preuve d'usage | Un usage déclaré n'est pas prouvé. Exception : le label *proven* de l'ADR `0094`, réservé à un paiement plus un reçu signé | *usage record*, *public record* |
| *registry* en accroche | Le mot le plus banal du marché (10 411 marketplaces) | *layer*, *record* |
| *trustless*, *guaranteed* | La triche est rendue chère, pas impossible | *costly to fake*, *anyone can recompute* |
| *reputation score* | Même raison que *score* | *reputation* seul, ou *standing* |

**Les mots à répéter** : *used*, *works*, *answers*, *open*, *recompute*, *agents*, *tools*, *money flows*.

## Un message par public

Chaque public entend une seule chose : ce qu'il y gagne aujourd'hui. Le but final reste le même pour tous, mais on ne commence jamais par lui.

| Public | Ce qu'il veut | Le message | La preuve à montrer |
| --- | --- | --- | --- |
| Développeurs d'agents | Que leur agent ne plante pas | *Know if a broken tool is your problem or everyone's.* | `arp status` en démo de 30 secondes |
| Auteurs d'outils et de skills | Être reconnus, distingués des copies | *Prove your tool is used, not just installed.* | La page de leur outil face à ses copies, avec le badge, gratuit |
| Opérateurs d'agents ERC-8004 | Sortir du lot des agents morts | *Show your agents answer, and what they run on.* | Le taux d'agents qui répondent, et les leurs dedans |
| Agrégateurs (Glama, HOL, 8004scan, Bazaar) | Une colonne de plus sans la construire | *Add a usage column you don't have to build.* | Le format des rapports et un adaptateur |
| Écosystème Intuition | Des usages réels du graphe | *The first live use case for agents on the graph.* | Le nombre de triples écrits par des agents tiers |
| Financeurs et programmes de subventions | Savoir où va leur argent | *Fund what agents actually depend on.* | La liste des outils les plus utilisés d'un écosystème |
| Investisseurs | Une ligne qui monte, vérifiable | *Every number I send you is recomputable from the graph.* | La mise à jour mensuelle et sa requête |

## Les objections et les réponses

Une réponse honnête et courte vaut mieux qu'une réponse qui esquive : les investisseurs testent surtout ta lucidité.

| Objection | Réponse |
| --- | --- |
| *« Un agent peut déclarer n'importe quoi. »* | Oui, et c'est pour ça qu'une déclaration est signée et attribuée, que la place d'un outil vient des dépôts des autres, et qu'ARP ne finance que les dépôts qui apportent une preuve. Sans preuve, c'est indexé comme *declared*, jamais *proven*. On compte par opérateur, pas par agent. |
| *« Pourquoi on chain ? »* | Pour que personne, ARP compris, ne puisse réécrire l'historique, et que n'importe qui puisse refaire les chiffres sans nous demander. Le privé reste sur la machine ; seul « cet agent utilise cet outil » devient public. |
| *« Glama, HOL ou AWS ajouteront la colonne. »* | Possible. Ils ne voient chacun qu'une facette et ont intérêt à leurs propres listings. Un registre neutre est plus crédible, et l'historique accumulé ne se copie pas. Le meilleur scénario est d'être leur source. |
| *« Qui paie ? »* | Les agents qui consultent ARP, en USDC via x402, sans compte. Les outils ne paient jamais : c'est ce qui garde ARP neutre. ARP achète le TRUST qu'il dépense pour financer les dépôts prouvés, et n'en vend jamais (ADR `0094`). |
| *« Les registres curatés par jetons ont tous échoué. »* | Ceux qui votaient sur des critères subjectifs, oui. Kleros Curate tient depuis 2019 sur des critères vérifiables. ARP ne fait pas voter sur la qualité : il enregistre un usage et une joignabilité que tout le monde peut vérifier. |
| *« Personne n'interroge les registres aujourd'hui. »* | C'est vrai pour les requêtes mesurées. C'est pourquoi le premier produit est utile à un développeur seul, et pourquoi la distribution passe par une skill et des plugins, là où les agents cherchent déjà des outils. |
| *« Le jeton TRUST a beaucoup baissé. »* | ARP ne dépend pas de son prix : la déclaration a un coût, pas une valeur spéculative. Les revenus sont en USDC. |
| *« Tu es seul. »* | Oui. Le dépôt montre la méthode, et le cœur du produit est déjà construit sur testnet. La première levée servira à recruter. |
| *« Quelle différence avec 8004scan ? »* | 8004scan compose un score à partir d'entrées gratuites. ARP ne note pas, et ses entrées coûtent quelque chose. On peut aussi leur fournir la donnée d'usage. |

## Le kit de lancement

Le lancement tient en une journée : le premier rapport sort, la skill et les plugins sont publiés le même jour, et chaque post renvoie vers les deux. Rien n'est annoncé avant que le rapport existe.

### Le rapport « State of agent tools », numéro 1

1. **Le chiffre d'ouverture** : combien d'agents ERC-8004 répondent vraiment, par chaîne, avec la méthode et la date.
2. **Les outils MCP** : la part qui répond, la part non maintenue, les plus utilisés.
3. **Les copies** : les skills dont des copies battent l'original en installations, en créditant les auteurs originaux.
4. **Ce qui a changé en douce** : les outils dont les fonctions ou l'hôte ont changé sous le même nom.
5. **La méthode** : les scripts, les dates, les données brutes, pour que n'importe qui refasse le calcul.
6. **La fin** : « Pour voir ça pour ton propre agent : `npx @arp-protocol/cli init` ».

Règle : factuel, sans moquerie, et aucun chiffre sans sa source.

### Le fil sur X

> 1/ I measured the AI agent tool ecosystem. Most of it doesn't work.
>
> 2/ Of [N] ERC-8004 agents sampled on Base, [X] answered a protocol handshake.
>
> 3/ On skills.sh, [N] repositories publish copies of the same skill. Several out-install the original.
>
> 4/ Stars show who looked. Installs show who downloaded. Neither shows who used it.
>
> 5/ So I'm building ARP: agents record each tool call that works, on an open graph anyone can read.
>
> 6/ Free for developers: `arp status` tells you if a broken tool is your problem or everyone's. Full report and method: [LINK]

### Show HN

> **Show HN: ARP, is it my agent, or is the MCP server broken for everyone?**
>
> I built a hook for Claude Code that logs each MCP tool call locally (tool, outcome, duration; never the content) and compares your success rate with other agents using the same tool. It also warns when a server changes its functions or host under the same name. The only thing that goes public is "this agent uses this tool, and it works", recorded on an open graph. Report on the state of agent tools, with method: [LINK]

### Reddit (r/mcp, r/ClaudeAI)

> **I measured how many MCP servers and agent skills actually work. Here's the data.**
>
> [Three findings, one line each.] Method and raw data: [LINK]. I also made a free hook that shows you which of your agent's tools are broken for everyone versus just for you. Feedback welcome.

### La description de la skill sur skills.sh

> **arp: check a tool before you use it**
>
> Before adding or calling an MCP server, skill or x402 endpoint, ask ARP whether it works for other agents, how many operators use it, and whether it changed recently. If it is broken everywhere, ARP lists what other agents switched to. Declaring what you used is optional and builds your agent's public record.

## Ce qui reste à produire avant le lancement

- [ ] **La démo de 30 secondes** : un outil casse, `arp status` dit « broken everywhere » et propose l'alternative. Enregistrée en vidéo d'écran.
- [ ] **Une page d'accueil** avec la phrase, la démo, la commande d'installation et l'inscription à la mise à jour mensuelle.
- [ ] **Une adresse e-mail de contact** à mettre sur la dernière slide du deck (`[YOUR EMAIL]`).
- [ ] **Le premier rapport**, avec des mesures refaites en novembre et leurs scripts.
- [ ] **La publication** de `@arp-protocol/cli` sur npm, des plugins Claude Code et Gemini, de la skill sur skills.sh, et du serveur MCP sur Smithery, Glama et le registre officiel.
- [ ] **Le domaine du badge et des pages par outil.**
- [x] **Corriger « proof of use »** en « public usage record » dans le plan de démarrage et la page de lecture.
- [ ] **Le post de demande de subvention** sur le forum Atlas d'Intuition, qui reprend la vision, le plan et le budget de la trésorerie de financement des dépôts.
