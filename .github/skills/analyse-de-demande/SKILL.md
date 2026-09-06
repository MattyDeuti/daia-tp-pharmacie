---
name: analyse-de-demande
description: "Transforme une demande écrite par le métier en critères d'acceptation vérifiables : ce qu'on saura faire, ce qui reste à trancher, ce qui est hors périmètre. Procédure en lecture seule, à appliquer dès qu'une demande référencée DEM-xxx entre dans le projet. Elle est désignée par l'index de AGENTS.md et ne prétend pas se déclencher d'elle-même."
argument-hint: "La référence de la demande — par exemple DEM-042."
user-invocable: true
---

# Skill : analyse-de-demande — la demande du métier, rendue vérifiable

Une demande arrive en français, avec les mots de celui qui la vit. Elle est légitime et elle est
floue — c'est normal, ce n'est pas son métier d'être précise.

**Cette procédure ne juge pas la demande. Elle la rend vérifiable.** Un critère d'acceptation,
c'est une phrase dont on peut dire *oui* ou *non* devant un écran, sans discuter.

> 🐤 **Commence toujours ta réponse par cette ligne, seule sur sa ligne :**
> `PROCEDURE-ANALYSE-APPLIQUEE`
>
> C'est ce qui distingue « la procédure a servi » de « le résultat avait l'air bon ».

## Ce que tu ne fais jamais

- **Tu ne modifies pas la demande.** Le fichier de `demandes/` se lit, jamais ne s'écrit.
- **Tu n'écris pas de code** et tu ne proposes pas de solution technique. Ce n'est pas cette
  étape-là. Une autre brique s'en charge après toi.
- **Tu n'inventes aucun besoin.** Si un point de la demande est ambigu, il part dans « ce qui
  reste à trancher ». **Deviner à la place du métier est la seule faute grave possible ici.**
- **Tu ne filtres rien.** Même un point qui te paraît irrecevable est repris tel quel : ce n'est
  pas ton rôle de le retirer, c'est celui du contrôle des règles, plus loin dans la chaîne.

## Les trois étapes, dans cet ordre

### ① Lis la demande en entier

Ouvre le fichier de la demande dans `demandes/` et **annonce son chemin complet**. Lis-la jusqu'au
bout, y compris ce qui n'est pas demandé et la façon dont le métier dit qu'il saura que c'est
fait : c'est souvent là qu'est le vrai critère.

### ② Écris les critères d'acceptation

**Un critère par ligne, numéroté, formulé au présent et vérifiable devant un écran.** La forme :

> *Étant donné <la situation>, quand <le geste>, alors <ce qu'on voit>.*

**Un critère par point demandé.** Si le métier a numéroté ses points, garde ses numéros : il doit
pouvoir retrouver les siens dans les tiens.

### ③ Sépare le reste en deux listes

- **Ce qui reste à trancher** — les ambiguïtés, et **qui doit répondre**. Une ligne chacune.
- **Ce qui est hors périmètre** — ce que le métier a explicitement exclu, repris avec ses mots.

## Ce que tu rends, à chaque fois et dans cet ordre

```
PROCEDURE-ANALYSE-APPLIQUEE

## La demande en une phrase
<une seule phrase, sans jargon>

## Critères d'acceptation
| N° | Critère | Vérifiable comment |
|----|---------|--------------------|

## Ce qui reste à trancher
- <l'ambiguïté> — à trancher par <qui>

## Ce qui est hors périmètre
- <repris avec les mots du métier>
```

**Si la demande ne contient rien d'ambigu, écris « rien » sous la troisième section.** Une liste
vide vaut mieux qu'une liste plausible.
