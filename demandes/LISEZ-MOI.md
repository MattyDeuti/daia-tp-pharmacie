# `demandes/` — les demandes du métier

**Vous n'avez rien à écrire ici, et rien à y modifier.**

Ce dossier contient les demandes telles qu'elles arrivent dans une officine : écrites par
quelqu'un qui ne programme pas, en français, sans vocabulaire technique. C'est le point d'entrée
d'un travail, pas son résultat.

| Fichier | Ce que c'est |
|---|---|
| `DEM-042.md` | **la demande de la démonstration du jour 2.** Tracer les sorties de stupéfiants |

## Pourquoi c'est figé

La démonstration de fin de jour 2 traite cette demande **en entier, en trois mots**. Pour que la
même chaîne rende le même résultat à chaque session, il faut que le sujet ne bouge jamais.

C'est aussi ce qui la distingue d'un exercice : une demande figée dans le dépôt ne dépend **de
rien** — ni de ce que vous avez codé hier, ni de ce que vous avez enregistré, ni de l'état de
votre branche. Elle est là, identique, et elle le restera.

> **La charte du projet interdit d'écrire dans ce dossier** *(règle dure n° ③)*. Un assistant
> qui vous propose de « corriger » la demande a désobéi : la demande du métier n'est pas à
> corriger, elle est à traiter.

## Ce que la démonstration en fait

Cinq briques du dépôt s'enchaînent sur cette seule demande, chacune avec son métier :

| | La brique | Ce qu'elle rend |
|---|---|---|
| ① | `.github/skills/analyse-de-demande/SKILL.md` | la demande en critères d'acceptation |
| ② | `.github/agents/explorateur-de-code.agent.md` | où ça touche dans le code, avec les chemins |
| ③ | `.github/agents/testeur-qa.agent.md` | ce qu'il faudra vérifier, geste par geste |
| ④ | `.github/agents/gardien-des-regles.agent.md` | le contrôle des trois règles dures |
| ⑤ | `.github/agents/traducteur-metier.agent.md` | la réponse à renvoyer à la pharmacienne |

**Le point ③ de la demande ne passera pas la brique ④**, et c'est voulu : la pharmacienne
demande le nom du patient dans le registre, et la charte l'interdit sans exception. Ce n'est ni
une erreur de sa part, ni un piège — **c'est ce qui arrive tous les jours dans une vraie
équipe**, et c'est précisément le travail que la couche fait à votre place.
