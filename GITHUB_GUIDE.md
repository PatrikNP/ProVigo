# 🚀 Snabbguide: Ladda upp ProVigo till GitHub

## Steg 1: Skapa GitHub Repository

1. Gå till https://github.com
2. Klicka på **"New repository"** (gröna knappen)
3. Namn: `provigo`
4. Beskrivning: `Personlig tränings- och hälsoapp med Firebase-synk`
5. Välj **Public**
6. **KRYSSA INTE I** "Add a README" (vi har redan en)
7. Klicka **"Create repository"**

## Steg 2: Förbered filerna

Skapa en ny mapp på din dator och lägg dessa filer där:

```
provigo/
├── index.html          ← ProVigo_Firebase_Final.html (döp om!)
├── icon.svg           
├── README.md          
└── .gitignore         
```

**VIKTIGT:** Döp `ProVigo_Firebase_Final.html` till `index.html`

## Steg 3: Ladda upp med Git

Öppna Terminal/Command Prompt i din `provigo`-mapp och kör:

```bash
# Initiera git
git init

# Lägg till alla filer
git add .

# Första commit
git commit -m "Initial commit - ProVigo app med Firebase"

# Byt till main branch
git branch -M main

# Koppla till GitHub (ersätt DITT-ANVÄNDARNAMN)
git remote add origin https://github.com/DITT-ANVÄNDARNAMN/provigo.git

# Pusha till GitHub
git push -u origin main
```

## Steg 4: Aktivera GitHub Pages

1. Gå till ditt repository på GitHub
2. Klicka på **Settings** (kugghjulet)
3. Klicka på **Pages** i vänstermenyn
4. Under **Source**:
   - Branch: `main`
   - Folder: `/ (root)`
5. Klicka **Save**

⏳ Vänta 1-2 minuter...

Din app finns nu på:
```
https://DITT-ANVÄNDARNAMN.github.io/provigo/
```

## Steg 5: Testa synkningen! 🎉

1. Öppna länken på din mobil
2. Öppna samma länk på din surfplatta
3. Logga en träning på mobilen
4. Se hur den dyker upp på surfplattan DIREKT! 💪

## 🔧 Om något går fel

### Git inte installerat?
- Windows: https://git-scm.com/download/win
- Mac: Öppna Terminal och skriv `git` (installeras automatiskt)

### Behöver hjälp med GitHub?
- GitHub Desktop: https://desktop.github.com/ (enklare GUI)

### Firebase-problem?
- Kontrollera att reglerna är korrekta i Firebase Console
- Öppna Console i webbläsaren (F12) och kolla efter fel

## 📱 Lägg till som app på mobilen

### iPhone/iPad:
1. Öppna sidan i Safari
2. Tryck på **Dela-knappen**
3. Välj **"Lägg till på hemskärmen"**
4. Nu har du ProVigo som en riktig app!

### Android:
1. Öppna sidan i Chrome
2. Tryck på **menyn** (tre prickar)
3. Välj **"Lägg till på startskärmen"**
4. Nu har du ProVigo som en riktig app!

---

🎊 **KLART!** Nu har du ProVigo med realtidssynk mellan alla dina enheter!
