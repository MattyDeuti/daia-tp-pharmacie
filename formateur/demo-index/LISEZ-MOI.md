# `formateur/demo-index/` — le fichier de la démonstration du jour 2

**Ce dossier n'est pas un exercice.** Vous n'avez rien à y faire et rien à y écrire. Il contient
le `AGENTS.md` que le formateur projette pendant la démonstration de fin de journée du jour 2,
**DÉMO 09 · L'index, montré pour de vrai**.

Vous pouvez l'ouvrir et le lire — c'est même le meilleur modèle du kit si vous voulez écrire le
vôtre en rentrant. Il tient en **143 lignes**, et c'est la seule chose qu'il faut retenir de sa
forme.

| Fichier | Ce que c'est |
|---|---|
| `AGENTS.md` | **le fichier de la démonstration** — canari en tête, contexte, trois règles dures, l'index |

Les six objets que son index désigne vivent, eux, à leur vraie place dans le projet :

| Fichier | Ce que c'est |
|---|---|
| `demandes/DEM-042.md` | **la demande du métier** — le sujet de la chaîne, figé dans le dépôt |
| `.github/skills/analyse-de-demande/SKILL.md` | ① la procédure qui rend la demande vérifiable |
| `.github/agents/explorateur-de-code.agent.md` | ② l'agent qui dit **où ça touche** |
| `.github/agents/testeur-qa.agent.md` | ③ l'agent qui écrit **ce qu'il faudra vérifier** |
| `.github/agents/gardien-des-regles.agent.md` | ④ l'agent qui **contrôle les trois règles dures** |
| `.github/agents/traducteur-metier.agent.md` | ⑤ l'agent qui **répond à la pharmacienne** |

---

## Note pour le formateur

### Pourquoi ce fichier n'est pas déjà à la racine

**Parce que le `AGENTS.md` de la racine appartient aux apprenants.** C'est le squelette à
sections qu'ils remplissent au cas pratique de fin de jour 2 — et celui qu'ils vident au cas
pratique du canari, le jour 1. Si la version de la démonstration s'y installait, les deux cas
pratiques n'auraient plus de sens.

D'où la manœuvre : on la copie le temps de la démonstration, on la retire après.

### Armer — avant la démonstration, jamais pendant

**Trois gestes, et il n'y en a plus quatre.**

```powershell
Copy-Item formateur\demo-index\AGENTS.md AGENTS.md -Force
Remove-Item livraison -Recurse -Force -ErrorAction SilentlyContinue
```

Puis **rechargez la fenêtre de l'éditeur** (`Ctrl + Maj + P` → *Developer: Reload Window*) et
**ouvrez une conversation neuve**. Sans ces deux gestes, l'outil travaille encore avec l'ancien
fichier et le canari ne sort pas.

> **La deuxième ligne n'est pas de la coquetterie.** L'effet de la démonstration tient à ce que
> le dossier `livraison/` se remplisse **à l'écran**, fichier après fichier. S'il est déjà plein
> du passage précédent, la salle ne voit rien naître. `livraison/` est en `.gitignore` : le
> vider n'a aucune conséquence.

> ⚠️ **Si l'outil du jour ne lit pas `AGENTS.md`** mais son propre nom de fichier, copiez-la
> aussi sous ce nom-là — `GEMINI.md`, `CLAUDE.md`, ou `.github/copilot-instructions.md` selon
> l'outil. **C'est à vérifier au drill, pas en séance.** Le même contenu marche dans les trois
> cas : c'est justement ce que dit le temps de la bascule.

### 🆕 Ce que cette version a supprimé, et pourquoi

**L'ancienne démonstration exigeait des modifications non publiées dans le dépôt** — trois
lignes changées quelque part, non enregistrées — parce que la chaîne portait sur *« ce qui a
changé »*. C'était **la seule condition matérielle**, et c'était celle qu'on oubliait.

Pire : c'était une condition **différentielle**. Elle n'existait que par rapport à l'état de la
veille, elle s'évaporait au premier `git checkout`, et elle obligeait à saboter le dépôt avant
chaque passage.

**La chaîne porte désormais sur une demande figée et versionnée**, `demandes/DEM-042.md`. Elle
est identique à chaque session, elle survit à un `git reset --hard`, et elle se rejoue deux fois
de suite dans la même séance sans rien préparer. **Il n'y a plus rien à saboter.**

### Les six marqueurs, et ce que chacun prouve

C'est ce qui rend la démonstration démontrable. Les six sont visibles à l'écran, dans cet ordre.

| Marqueur | Où il apparaît | Ce qu'il prouve |
|---|---|---|
| `CHARTE-PHARMASTOCK-LUE` | première ligne de **la toute première réponse** | le fichier a été relu **avant** qu'on demande quoi que ce soit |
| `PROCEDURE-ANALYSE-APPLIQUEE` | en tête de l'analyse | la procédure a réellement été ouverte, pas devinée |
| `AGENT-EXPLORATEUR-CODE` | en tête du relevé technique | le premier agent a réellement été lancé |
| `AGENT-TESTEUR-QA` | en tête du plan de vérification | le deuxième aussi |
| `AGENT-GARDIEN-DES-REGLES` | en tête du contrôle | le troisième aussi — **et c'est lui qui trouve** |
| `AGENT-TRADUCTEUR-METIER` | en tête de la réponse au métier | le quatrième aussi |

**Aucun des six n'a été nommé dans la demande.** On a tapé `go DEM-042`. C'est tout le propos :
montrez-les en remontant le fil, dans cet ordre.

### Ce que le gardien doit trouver — et pourquoi c'est fiable

Le point ③ de `DEM-042.md` demande **le nom du patient dans le registre**. La règle dure ① de la
charte l'interdit sans exception. **L'accroche est écrite dans deux fichiers committés** : elle
ne dépend de rien d'autre, et elle sera encore là dans six mois.

Le verdict attendu est **CONFORME SOUS RÉSERVE**, pas *NON CONFORME* : le besoin est légitime,
c'est sa formulation qui accroche. La reformulation conforme existe — tracer l'identifiant de
l'ordonnance ou du mouvement au lieu du nom. **C'est le cœur de la démonstration : la couche ne
bloque pas, elle redresse.**

### Désarmer — juste après, avant de toucher à quoi que ce soit

```powershell
git checkout -- AGENTS.md
git status
```

Le `git status` n'est pas de la précaution excessive : **le fichier de la racine ne doit jamais
partir dans un commit.** S'il y arrivait, tous les apprenants récupéreraient une charte déjà
remplie au prochain `git pull`, et les deux cas pratiques qui s'appuient dessus tomberaient.

`livraison/` étant en `.gitignore`, il n'y a rien d'autre à nettoyer.

### Le déroulé

**Il n'est pas dans ce dépôt** : les fiches de déroulé vivent côté formateur, dans
`Big Training/demos/`, sous le nom `DEMO09 · L'index, montré pour de vrai` — avec les temps
minutés, ce qu'on montre, les plans B et la liste de contrôle du drill.

**Les demandes seules, prêtes à coller, sont dans le dépôt** :
`formateur/prompt_demo/J2-slide232-demo9.md`.

### Une skill qui n'est plus dans cet index, et c'est normal

`.github/skills/resume-des-modifications/SKILL.md` **n'est plus désigné par le `AGENTS.md` de la
démonstration** — c'est lui qui portait l'ancienne chaîne sur « ce qui a changé ». Il reste dans
le dépôt et **il sert toujours** : le cas pratique de la couche d'équipe s'appuie dessus
(`apprenant/prompt_tp/J2-slide206-couche-equipe/brique-2-procedure-de-tests.md`). Ne le
supprimez pas.
