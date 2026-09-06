# DÉMO 09 · L'index — ce qu'on tape, dans l'ordre

*Déroulé, marqueurs attendus, plans B et drill : côté formateur, dans `Big Training/demos/`.*

---

### ① ARMER · terminal

```powershell
Copy-Item formateur\demo-index\AGENTS.md AGENTS.md -Force
Remove-Item livraison -Recurse -Force -ErrorAction SilentlyContinue
```

Puis **Reload Window** (`Ctrl+Maj+P`), puis **conversation neuve**. Explorateur ouvert à gauche.

### ② LE CANARI · panneau

```
Bonjour. En deux phrases, ce projet sert à quoi ?
```

→ `CHARTE-PHARMASTOCK-LUE`. **S'il ne sort pas, on s'arrête là.**

### ③ LE GO · panneau

```
go DEM-042
```

→ 6 marqueurs, 5 fichiers dans `livraison/DEM-042/`. On ouvre en grand `5-reponse-au-metier.md`.

### ④ LE CONTRE-EXEMPLE · panneau

*Annoncer avant d'envoyer qu'on attend que rien ne se déclenche.*

```
Il faut qu'on migre la base vers un autre moteur. Par où on commence ?
```

→ le canari, et rien d'autre.

### ⑤ LE CLEAR · jauge, panneau, terminal, panneau

```
/clear
```

```powershell
Remove-Item livraison -Recurse -Force
```

```
go DEM-042
```

### ⑥ DÉSARMER · terminal, tout de suite après

```powershell
git checkout -- AGENTS.md
git status
```
