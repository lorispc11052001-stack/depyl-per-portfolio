# Setup pulito in VS Code (anti-cartelle incasinate)

## Qual è la cartella GIUSTA da aprire
Apri **solo** la cartella che contiene contemporaneamente:
- `.git`
- `index.html`
- `assets/`
- `dist/`

Nel tuo caso corretto è la root del progetto:
`depyl-per-portfolio/`

## Se vedi una seconda cartella `depyl-per-portfolio` dentro la prima
Quella interna è una copia annidata (sbagliata) e va rimossa.

Comandi (da root progetto):

```bash
pwd
git rev-parse --show-toplevel
find . -maxdepth 2 -type d -name .git
```

Se l'ultimo comando mostra **solo** `./.git`, sei pulito.
Se mostra anche `./depyl-per-portfolio/.git`, elimina la cartella annidata.

## Come verificare che sei sul branch corretto
```bash
git branch --show-current
git status
git log --oneline -n 5
```

## CSS: file unico da controllare
Le pagine HTML puntano tutte a `dist/css/sass.css`.
Se modifichi gli stili, verifica di salvare/compilare verso quel file.

## Aprire subito il sito
Da root progetto:
```bash
python -m http.server 4173
```
Poi apri:
- `http://localhost:4173/index.html`
