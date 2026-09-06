# Démo 9 · L'index, montré pour de vrai

> **MODE : AGENT** · session neuve, à la racine du kit

*Jour 2, fin d'après-midi · **un modèle de tête** (voir l'encadré ci-dessous), session neuve, à
la racine du kit*

> **Avant d'ouvrir la bouche : le fichier est-il armé ?**
>
> ```powershell
> Copy-Item formateur\demo-index\AGENTS.md AGENTS.md -Force
> Remove-Item livraison -Recurse -Force -ErrorAction SilentlyContinue
> ```
>
> Puis *Reload Window*, puis **conversation neuve**. Le mode d'emploi complet est dans
> `formateur/demo-index/LISEZ-MOI.md`.
>
> **Il n'y a plus rien d'autre à préparer.** Pas de modifications non publiées, pas de dépôt
> sali : la chaîne porte sur `demandes/DEM-042.md`, qui est committé et ne bouge jamais.

> ⚠️ **Le choix du modèle n'est plus indifférent.** L'ancienne chaîne avait deux étapes ; celle-ci
> en a cinq et délègue à quatre agents. **Un petit modèle rapide saute des étapes** — il fera
> deux briques sur cinq et rendra quelque chose de plausible. Prenez le meilleur modèle
> disponible dans Copilot ce jour-là, et **tranchez au drill, pas en salle**.

---

## 🖥 La mise en scène — à faire AVANT le temps 1

**L'explorateur de fichiers reste ouvert à gauche, dépliez `livraison/`.** C'est le deuxième
écran de la démonstration, et pour la moitié de la salle c'est le seul qui parle : ils ne lisent
pas le chat, ils voient des fichiers naître.

---

## Temps 1 · le fichier, à l'écran

**Rien à taper.** On ouvre `AGENTS.md` à la racine et on descend dedans en le commentant : le
canari en tête, le contexte, les trois règles dures, l'index. Trois minutes.

La phrase à lire à voix haute, elle est écrite dans le fichier :

> *Ce fichier ne sait rien faire. Il sait où sont ceux qui savent.*

**Puis on s'arrête sur les cinq étapes numérotées de l'index**, et on dit la phrase qui prépare
tout le reste :

> *Cinq étapes, cinq briques, écrites une fois. On tape trois mots, et c'est le même processus à
> chaque fois.*

---

## Temps 2 · le canari, au premier message

**Une question quelconque. C'est tout l'intérêt : on ne demande rien de spécial.**

**📋 À COLLER DANS LE PANNEAU**

```
Bonjour. En deux phrases, ce projet sert à quoi ?
```

**Ce qu'on attend :** la réponse commence par `CHARTE-PHARMASTOCK-LUE`, seule sur sa ligne.

⛔ **Ne pas demander « as-tu lu la charte ? ».** C'est exactement ce qu'on a interdit à la salle
pendant deux jours.

---

## Temps 3 · le GO

**Le sommet de la démonstration. Trois mots, et on ne dit plus rien pendant deux minutes.**

**📋 À COLLER DANS LE PANNEAU**

```
go DEM-042
```

> **Annoncez AVANT d'envoyer ce que vous attendez** — sinon les deux minutes de cascade se
> passent dans un silence inquiet. Une phrase : *« je tape trois mots, et je ne prononce le nom
> d'aucun outil. Comptez les métiers qui vont travailler. »*

**Ce qu'on attend, dans cet ordre, et c'est la preuve :**

| | Ce qui doit apparaître | Le fichier qui naît à gauche |
|---|---|---|
| 1 | `CHARTE-PHARMASTOCK-LUE` | — |
| 2 | `PROCEDURE-ANALYSE-APPLIQUEE`, puis les critères | `livraison/DEM-042/1-analyse.md` |
| 3 | `AGENT-EXPLORATEUR-CODE`, puis les chemins réels | `2-impact-technique.md` |
| 4 | `AGENT-TESTEUR-QA`, puis le plan de vérification | `3-plan-de-verification.md` |
| 5 | `AGENT-GARDIEN-DES-REGLES`, puis **CONFORME SOUS RÉSERVE** | `4-controle-des-regles.md` |
| 6 | `AGENT-TRADUCTEUR-METIER`, puis la réponse en français | `5-reponse-au-metier.md` |

**Nommez chaque agent à voix haute quand il apparaît**, et rien de plus : *« là, c'est le
développeur. Là, c'est le testeur. Là, c'est la conformité. »* Le silence se remplit tout seul.

### 🔴 Le moment qui porte la démonstration — l'étape 5

**Arrêtez-vous sur le verdict du gardien.** La pharmacienne a demandé le nom du patient dans le
registre. La règle ① de la charte l'interdit. **Il ne bloque pas : il propose de tracer
l'ordonnance à la place.**

La phrase, et le silence après :

> *Personne n'a relu cette demande. La règle était écrite une fois, dans un fichier, et elle
> vient de tenir toute seule — sur une demande faite de bonne foi par la patronne.*

### Le geste de preuve, avant de commenter

**On remonte le fil et on montre les six marqueurs dans l'ordre.** Puis on ouvre en grand
`livraison/DEM-042/5-reponse-au-metier.md` — **la seule page qu'un humain enverrait vraiment.**

> *J'ai nommé une demande. Je n'ai nommé aucune des cinq briques qui viennent de travailler.
> C'est l'index qui savait où les trouver.*

---

## Temps 4 · le contre-exemple

**Annoncer AVANT de l'envoyer qu'on attend que rien ne se déclenche.** Sinon la salle croit à un
raté.

**📋 À COLLER DANS LE PANNEAU**

```
Il faut qu'on migre la base vers un autre moteur. Par où on commence ?
```

**Ce qu'on attend :** le canari sort — le fichier a bien été relu — **et rien d'autre ne se
déclenche.** Ni procédure, ni agent, aucun fichier dans `livraison/`. Il répond de lui-même,
comme n'importe quel assistant.

Puis on remonte dans `AGENTS.md`, à la section **« Ce qui n'est pas dans l'index »**, et on la lit
à l'écran. **Le fichier avait annoncé ce comportement.**

---

## Temps 5 · la bascule

**Rien à taper, et la meilleure preuve est derrière eux.**

Il y a vingt-cinq minutes, toute la salle a tapé `sauvegarde et publie mon travail` — et une
procédure que **personne n'avait installée** s'est saisie du travail sur chaque poste. Elle était
dans le dossier qu'on leur a donné : `.github/skills/git-workflow/SKILL.md`.

C'est ça, la bascule, et ils l'ont déjà vécue sans la nommer.

---

## Temps 6 · le clear qui ne coûte rien

**Montrer la jauge de contexte AVANT.** Sans le chiffre à l'écran, le moment ne prouve rien.

**📋 À COLLER DANS LE PANNEAU**

```
/clear
```

**Montrer la jauge APRÈS.** Videz `livraison/` dans le terminal, puis recollez **exactement** les
trois mots du temps 3 :

**⌨️ À TAPER DANS LE TERMINAL**

```
Remove-Item livraison -Recurse -Force
```

**📋 À COLLER DANS LE PANNEAU**

```
go DEM-042
```

**Ce qu'on attend :** les six marqueurs reviennent, dans le même ordre, et les cinq fichiers
renaissent. **Cinq briques, comportement identique, avec une fraction du contexte.**

---

## Après — désarmer, tout de suite

**⌨️ À TAPER DANS LE TERMINAL**

```
git checkout -- AGENTS.md
git status
```

**Le `AGENTS.md` de la racine ne doit jamais partir dans un commit :** c'est le squelette que les
apprenants remplissent. `livraison/` est en `.gitignore`, il n'y a rien d'autre à nettoyer.
