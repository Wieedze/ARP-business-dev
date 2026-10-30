# ARP : plan de démarrage

29 octobre 2026. Copie versionnée du document Claude « ARP : plan de démarrage ».

## En bref

ARP devient le registre public d'usage des outils d'agents : un enregistrement public de ce que les agents utilisent vraiment, à côté des étoiles, installs, disponibilité et paiements. Objectif d'ici fin février 2027 : des agents qu'on ne connaît pas qui déclarent leurs outils chaque semaine.

**Elevator pitch**

> *There are 48,000 MCP servers and 1.5 million registered agents, and nobody can tell which tools agents actually use. Stars and installs show who looked; reviews are mostly fake accounts. ARP records what agents really use, each time a call succeeds, on an open graph anyone can read, next to every other signal. Stars show who looked. ARP shows who used it.*

**Le résumé en cinq lignes**

1. **Le problème.** Des dizaines de milliers d'outils, environ la moitié qui ne répondent pas, et aucun signal d'usage réel.
2. **La place libre.** Chacun voit une facette ; personne ne garde une trace publique de l'usage réel.
3. **La cible d'abord.** Les constructeurs d'agents et les auteurs d'outils MCP et de skills, via Intuition et la communauté ERC-8004.
4. **Comment avoir les premiers utilisateurs.** Un hook gratuit dans les frameworks d'agents, un badge pour les auteurs, des frais subventionnés.
5. **Comment gagner de l'argent ensuite.** Le badge payé par les éditeurs, puis la donnée d'usage pour les agrégateurs.

## Le marché vu de l'extérieur

Chaque acteur voit une seule facette des agents et de leurs outils ; personne ne réunit popularité, disponibilité, paiements et usage déclaré sur une fiche publique et datée. C'est la place d'ARP.

| Segment | Qui y est, livré | Ce qu'il voit | Modèle |
| --- | --- | --- | --- |
| Annuaires d'outils MCP et de skills | [Registre MCP officiel](https://modelcontextprotocol.io/registry/registry-aggregators), [Glama](https://glama.ai/mcp/servers), Smithery (racheté par Arcade), [skills.sh](https://skills.sh/) | Ce qui existe, installs, notes de qualité | Gratuit, monétisé par l'hébergement |
| Découverte par le paiement | [Bazaar x402](https://docs.cdp.coinbase.com/x402/bazaar) (Coinbase) | Appels payés et payeurs uniques sur 30 jours | Gratuit, sert le rail de paiement |
| Agrégateur multi registres | [HOL Registry Broker](https://hol.org/docs/registry-broker/search) | Agents de 15 registres, disponibilité | API, partiellement à crédits |
| Registres d'entreprise | AWS Agent Registry, Microsoft Agent 365, Google Agent Registry | L'inventaire interne d'une entreprise | Facturé à l'usage ou par siège |
| Sécurité des outils | Snyk (Invariant), Socket, Runlayer | Vulnérabilités, code malveillant | Abonnement entreprise |
| Identité et avis on chain | [ERC-8004](https://www.8004scan.io/), Kleros Scout, Olas, Virtuals | Qui est enregistré, avis déclarés | Jetons, frais, subventions |
| Modèles et Spaces | Hugging Face Hub, avec des Spaces Gradio qui exposent un serveur MCP | Téléchargements, likes, dernière modification | Gratuit, monétisé par le calcul et les abonnements |

Trois constats tirés de la recherche du 29 octobre 2026 :

1. **L'offre explose.** Le registre MCP officiel est passé de 1 204 noms fin 2025 à 47 879 le 21 octobre 2026, et ERC-8004 compte 1,57 million d'identités.
2. **La qualité ne suit pas.** Environ la moitié des serveurs MCP répondent au handshake, et entre 3 et 15 % des agents ERC-8004 selon la chaîne. Dans le registre ERC-8004, 59 à 91 % des avis viennent de comptes sybil.
3. **Personne ne publie d'historique.** Chaque source montre l'état du moment ; aucune ne garde une trace publique de ce qui a été réellement utilisé, par qui, et si ça a marché.

Les chiffres détaillés et leurs sources sont dans `research/market-gap-report.md`.

## Positionnement marketing

ARP se présente comme le registre public d'usage des outils d'agents : une étoile dit qui a regardé, ARP montre qui s'en est servi et si ça a marché. Le contenu de marque reste en anglais.

**La phrase principale :** *Stars show who looked. ARP shows who used it.*

**La phrase longue :** *ARP is the public usage record for AI agents and their tools. Agents record what they actually used, on an open graph anyone can read, next to every other signal: installs, stars, uptime, paid calls.*

**La catégorie :** public usage record, le registre public d'usage. Le mot « registry » seul ne distingue plus rien, « réputation » sonne comme une note de plus, et « preuve » promet ce que le protocole ne prouve pas.

**Le périmètre :** ARP indexe ce qu'un agent peut appeler (serveurs MCP, skills, agents ERC-8004, endpoints x402, Spaces Hugging Face qui exposent un serveur MCP) et affiche à côté tous les signaux publics qui existent sur cet objet. GitHub, npm, Hugging Face, le Bazaar et HOL deviennent des colonnes de la fiche, pas des périmètres. Les modèles et les datasets apparaissent comme signal de popularité, sans devenir des objets ARP.

**Contre quoi on se définit.**

| Ce qui existe | Ce que ça dit | Ce qu'ARP ajoute |
| --- | --- | --- |
| Étoiles GitHub, installs npm et skills | Quelqu'un a regardé ou installé | Un agent l'a appelé, et l'appel a marché |
| Registres et annuaires | L'outil existe | Il est utilisé, par combien d'agents distincts |
| Avis et notes | Quelqu'un a donné son avis | Un usage réel, signé et daté |
| Tableaux de bord privés | L'état du moment, chez un fournisseur | Un historique public que personne ne peut réécrire |

**Les messages par public.**

1. **Constructeurs d'agents.** *Pick tools other agents actually use.* Un appel avant de choisir un outil, gratuit, lisible par l'agent lui même.
2. **Auteurs d'outils MCP et de skills.** *Prove your tool is used, not just installed.* Un badge qui affiche l'usage réel et distingue l'original de ses copies.
3. **Registres et agrégateurs** (Bazaar, HOL, Glama, 8004scan). *Add a usage column you don't have to build.* Une source de données ouverte, sans exclusivité.
4. **Écosystème Intuition.** *The first live use case for agents on the graph.* Du trafic réel d'agents qui écrivent des triples, ce que l'écosystème cherche à montrer.

**Ce qu'on ne promet pas.** ARP ne note personne et ne garantit pas qu'un outil est sûr. La phrase « utilisé et ça a marché » suffit, et elle se vérifie.

## Sur qui s'appuyer

Tes deux appuis naturels sont Intuition, où tu as déjà obtenu une subvention avec Sofia, et la communauté ERC-8004, dont la réputation est vide et envahie de faux comptes. La plupart des gros programmes de subventions sont fermés en ce moment.

**Subventions et financement**

| Programme | État au 29 oct. 2026 | Montant | Action |
| --- | --- | --- | --- |
| [Intuition Box, Atlas forum](https://atlas.discourse.group/c/ecosystem-development/grant-applications/36) | Ouvert en continu, candidature par post public | Cohorte 1 : 100k USDT pour 9 équipes ([annonce](https://intuition.box/blog/grant-recipients-cohort-1)) | Poster maintenant, avec des jalons chiffrés |
| [Base Builder Grants](https://docs.base.org/get-started/get-funded) | Pas de formulaire, l'équipe Base choisit ceux qui livrent en public | 1 à 5 ETH | Livrer et publier sur Base, se faire nommer |
| [Base Batches](https://www.base.org/batches) | Batch 004 fermé le 10 sept. ; prochain probablement fév. ou mars 2027, non confirmé | 100k $ | Préparer le dossier pour 2027 |
| [Ethereum Foundation, ESP](https://esp.ethereum.foundation/applicants) | Seulement sur appels à projets ; aucun sur les agents | Variable | Réserver des Office Hours ; suivre l'[équipe IA de l'EF](https://ai.ethereum.foundation/) |
| [Bourse French Tech](https://www.legalstart.fr/fiches-pratiques/aides-creation-entreprise/bourse-french-tech/) (Bpifrance) | Ouvert ; éligibilité d'une micro entreprise non confirmée | Jusqu'à 30 k€, 70 % des dépenses | Appeler Bpifrance Marseille |
| Gitcoin, Optimism, Coinbase CDP, MetaMask | Fermés ou inactifs en 2026 | | Ne pas y passer de temps |

**Communautés et partenaires de données**

| Qui | Pourquoi | Ce que tu leur apportes |
| --- | --- | --- |
| Auteurs d'ERC-8004 : Marco De Rossi (MetaMask), Davide Crapis (EF) ; [8004.org](https://www.8004.org/), [Telegram](https://t.me/ERC8004), [fil Ethereum Magicians](https://ethereum-magicians.org/t/erc-8004-trustless-agents/25098) | La réputation de leur norme ne marche pas, une étude le montre ([arXiv 2606.26028](https://arxiv.org/abs/2606.26028)) | Un signal d'usage réel au lieu d'avis gratuits |
| [8004scan](https://8004scan.io/), tenu par AltLayer | Il définit les [conventions des données de feedback](https://best-practices.8004scan.io/docs/02-feedback-standard.html) | Proposer un profil « usage d'outil » dans leur [suivi de tickets](https://github.com/alt-research/8004scan-issue-tracker) |
| [Registre MCP officiel](https://modelcontextprotocol.io/registry/registry-aggregators) | Il accepte des sous registres qui ajoutent leurs champs dans `_meta` | Une colonne d'usage sur chaque serveur MCP |
| [HOL Registry Broker](https://hol.org/registry/docs) | Il agrège 15 registres ; une offre d'adaptateur est déjà ouverte ([issue 20](https://github.com/hashgraph-online/registry-broker-skills/issues/20)) | Un adaptateur qui leur fournit l'usage ARP |
| Projets voisins sur Intuition (AgentId, AgentWitness, [forum Atlas](https://atlas.discourse.group/c/ecosystem-development/31)) | Même terrain, même financeur | S'intégrer plutôt que se concurrencer |
| Frameworks d'agents : [ElizaOS](https://docs.elizaos.ai/guides/publish-a-plugin), [Lucid Agents SDK de Daydreams](https://smithery.ai/skills/daydreamsai/lucid-agents-sdk) | Le hook s'installe une fois dans le framework, puis tous les agents l'ont | Un plugin prêt à l'emploi |

**Événements confirmés**

| Date | Événement | Intérêt |
| --- | --- | --- |
| 3 au 6 nov. 2026 | [Devcon 8, Mumbai](https://blog.ethereum.org/2025/12/23/devcon-mumbai) | Un espace agents est [proposé](https://forum.devcon.org/t/devcon-8-india-agentic-hub/8949), non confirmé |
| 12 au 15 avr. 2027 | [EthCC, Cannes](https://en.palaisdesfestivals.com/offers/ethereum-community-conference-cannes-en-5198662/) | À deux heures de Marseille : le moment de la démo |
| 28 au 30 mai 2027 | [ETHPrague](https://ethprague.com/) | Hackathon Ethereum et IA |
| 16 au 19 juin 2027 | [VivaTech, Paris](https://dealroom.co/events/vivatech-2027/) | Visibilité en France |

Les hackathons [ETHGlobal](https://ethglobal.com/events) récompensent déjà ERC-8004 et x402 dans leurs prix ; un hackathon de l'hiver peut servir de premier test public.

## Premiers utilisateurs

Les dix premiers utilisateurs se trouvent là où tu es déjà connu : l'écosystème Intuition et Sofia, puis les opérateurs d'agents ERC-8004 visibles dans tes propres mesures. L'offre d'entrée est gratuite et prend cinq minutes.

| Cercle | Qui exactement | Comment les atteindre | Offre d'entrée |
| --- | --- | --- | --- |
| 1. Proches | Testeurs alpha de Sofia, équipes financées par Intuition | Message direct, forum Atlas | Le hook installé avec toi en appel, frais payés par ARP |
| 2. Opérateurs d'agents | Les deux opérateurs qui dominent tes échantillons Base : centralcity.ai et les opérateurs de la marketplace Olas | Message direct, Telegram ERC-8004 | Import gratuit de leurs agents et badge « used by N agents » |
| 3. Auteurs d'outils | Auteurs de skills dont tu as repéré les copies (dont obra/superpowers), auteurs de serveurs MCP populaires | Issue GitHub ou message court | Une page qui montre l'original face à ses copies, avec le badge |
| 4. Frameworks | ElizaOS, Lucid Agents SDK de Daydreams | Plugin publié dans leur registre | Le hook en une ligne de configuration |
| 5. Communauté | Lecteurs du fil ERC-8004 et de 8004scan | Un rapport hebdomadaire public | « Cette semaine : quels outils les agents ont vraiment utilisés » |

**Trois leçons de projets comparables.**

1. **DefiLlama** laisse chaque projet soumettre son propre adaptateur sur [GitHub](https://github.com/DefiLlama/DefiLlama-Adapters) : les projets font le travail d'intégration eux mêmes. Même idée pour les hooks ARP.
2. **shields.io** s'est répandu par les badges dans les README : chaque projet qui l'affiche fait sa promotion.
3. **mcp.so** a ouvert huit jours après le lancement de MCP : arriver tôt sur un standard neuf compte plus que la perfection.

## Plan jusqu'à EthCC

D'ici fin février 2027, ARP doit passer de zéro à cent agents distincts qui déclarent leurs outils, dont la majorité ne t'appartient pas. Novembre sert à construire ; les portes se comptent à partir de la mise en ligne du hook, pas du calendrier. Le détail en liste est dans `plan/next-steps.md`.

| Phase | Livrables | Porte de sortie |
| --- | --- | --- |
| Construire (novembre 2026) | Hook gratuit et badge ; page publique des fiches ; subvention Intuition postée ; appel à Bpifrance | |
| Semer (déc. 2026 à mi janv. 2027) | 10 proches avec le hook ; message aux opérateurs ; premier rapport public ; hackathon ETHGlobal si possible | 10 agents tiers, six semaines après la mise en ligne |
| Brancher (mi janv. à fin févr. 2027) | Plugins ElizaOS et Daydreams ; registre MCP et Spaces HF ; adaptateur proposé à HOL ; rapport hebdo | 100 agents distincts |
| Prouver (mars 2027) | Test du badge à 1 € ; profil d'usage 8004scan ; bilan go ou pivot ; démo pour EthCC, avril 2027 | |

Indicateur principal : déclarations par semaine venant d'adresses que tu ne contrôles pas.

Si la première porte n'est pas franchie six semaines après la mise en ligne, on ne passe pas aux intégrations : on retourne voir les dix proches pour comprendre ce qui bloque. Un levier qui prend (un framework qui intègre le hook, un rapport qui circule, un hackathon) peut faire franchir la porte plus tôt, mais le plan ne compte pas dessus.

## Modèle économique

Jusqu'à fin février 2027, ARP ne cherche pas de revenu : il cherche la preuve que des agents qu'on ne connaît pas s'en servent. L'argent vient des subventions, puis de tests de prix volontairement petits.

| Phase | Source d'argent | Ce qu'elle prouve |
| --- | --- | --- |
| Nov. 2026 à févr. 2027 | Subventions d'écosystème (Intuition d'abord), frais de déclaration subventionnés | Que l'usage existe |
| Mars à juin 2027 | Badge « vérifié » ou mise en avant payée par l'auteur d'un outil ou l'opérateur d'agents, autour de 1 € par agent et par mois | Qu'un éditeur paie pour être visible |
| Mars à juin 2027 | Paiement à la requête en x402 pour l'API, quelques centimes par vérification | Qu'un agent paie lui même pour décider |
| Au delà | Licence des données d'usage aux agrégateurs et aux registres d'entreprise | Que les gardiens paient la donnée |

Le précédent le plus proche est celui des sites d'avis : c'est l'entreprise notée qui paie pour sa visibilité, pas le lecteur. Trustpilot a déclaré 261 M$ de revenus en 2025 sur ce modèle.

**Signaux d'accélération :** des déclarations d'adresses que tu ne contrôles pas chaque semaine, un premier éditeur qui paie le badge sans relance, un agrégateur qui demande l'accès aux données.

**Signaux d'arrêt ou de pivot :** fin février 2027, plus de 90 % des déclarations viennent de tes propres agents, ou aucun éditeur ne paie même 1 € après avoir vu son badge.

## Risques

Le risque principal n'est pas technique : c'est de construire une trace d'usage que seuls tes propres agents alimentent. Chaque risque a un indicateur qui le rend visible tôt.

| Risque | Ce qui le déclencherait | Indicateur à suivre | Parade |
| --- | --- | --- | --- |
| Personne ne déclare | Aucun agent tiers n'installe le hook | Part des déclarations venant d'autres adresses que les tiennes | Hook gratuit, frais subventionnés, badge comme récompense |
| Gonflement de l'usage | Un auteur fait tourner ses agents sur son propre outil | Agents distincts par outil, regroupés par opérateur | Compter les agents distincts et le retour dans le temps, pas les appels |
| Coût des écritures on chain | Une position par appel | Frais TRUST par semaine | Une position au premier usage réussi, puis une mise à jour par semaine |
| Un gros acteur ajoute la colonne | Glama, HOL ou AWS affichent un usage | Annonces des agrégateurs | Être leur source avant qu'ils construisent la leur ; l'historique on chain ne se copie pas |
| Dépendance aux sources tierces | Une API change ou ferme | Taux d'erreur de l'ingestion | Mettre en cache, lire leurs conditions d'utilisation, citer chaque source |
| Fatigue du fondateur seul | ARP et Sofia en parallèle | Heures par semaine sur ARP | Un objectif par semaine, un seul indicateur principal |

**Sources.** `research/market-gap-report.md` (chiffres et liens détaillés) ; [Coinbase CDP, Bazaar](https://docs.cdp.coinbase.com/x402/bazaar) ; [HOL, Registry Broker](https://hol.org/docs/registry-broker/search) ; [arXiv 2606.26028](https://arxiv.org/abs/2606.26028) ; [gstack office-hours](https://codex.danielvaughan.com/2026/03/30/gstack-garry-tan-production-skills-toolkit/).
