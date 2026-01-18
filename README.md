# 💪 ProVigo - Personlig Tränings & Hälsoassistent

ProVigo är en komplett tränings- och hälsoapp med Firebase-synkronisering för att hålla din data synkad mellan alla dina enheter.

## ✨ Funktioner

### 🏋️ Träning
- **Push/Pull/Ben/Löpning** - Kompletta träningsprogram
- **Detaljerad loggning** - Spara vikter, reps och sets för varje övning
- **Träningshistorik** - Se all din tidigare träning
- **Kalender** - Visuell översikt över genomförda pass
- **Statistik** - Streak-räkning och månadsstatistik

### 🍎 Kost & Näring
- **Måltidsplanering** - Komplett veckoplanering
- **Kaloriräkning** - Automatisk beräkning av dagliga kalorier
- **Proteinuppföljning** - Se hur mycket protein du får i dig
- **Flexibla mellanmål** - Lägg till och ta bort snacks efter behov

### ⚖️ Viktutveckling
- **Viktloggning** - Spara vikt över tid
- **Midjemått** - Följ även midjemått
- **Grafer** - Visuell viktutveckling
- **Trendanalys** - Se förändring mellan mätningar

### 👥 Profiler
- **Flera användare** - Skapa profiler för hela familjen
- **Separata data** - Varje profil har sin egen data
- **Enkel profilväxling** - Byt mellan profiler smidigt

### 🔥 Firebase Synkronisering
- **Realtidssynk** - Data synkas direkt mellan alla enheter
- **Offline-support** - Fungerar även utan internet
- **Automatisk backup** - All data sparas säkert i molnet

## 🚀 Installation

### 1. Ladda upp till GitHub

Skapa ett nytt repository på GitHub och ladda upp dessa filer:

```bash
git init
git add .
git commit -m "Initial commit - ProVigo app"
git branch -M main
git remote add origin https://github.com/DITT-ANVÄNDARNAMN/provigo.git
git push -u origin main
```

### 2. Aktivera GitHub Pages

1. Gå till ditt repository på GitHub
2. Klicka på **Settings**
3. Scrolla ner till **Pages** i menyn till vänster
4. Under **Source**, välj `main` branch
5. Klicka **Save**
6. Din app finns nu på: `https://DITT-ANVÄNDARNAMN.github.io/provigo/`

### 3. Firebase (Redan konfigurerat!)

Firebase är redan konfigurerat i appen med din befintliga databas:
- Database: `patrikapps-cd169`
- Region: `europe-west1`

**Viktigt:** Kontrollera att Firebase Realtime Database-reglerna är korrekta:

```json
{
  "rules": {
    "provigo": {
      ".read": true,
      ".write": true
    }
  }
}
```

⚠️ **OBS:** Dessa regler tillåter alla att läsa/skriva. För produktion, lägg till autentisering!

## 📱 Användning

### Öppna appen på flera enheter
1. Öppna appen på din mobil
2. Öppna samma URL på din surfplatta
3. Logga träning på en enhet → syns direkt på den andra!

### Skapa ny profil
1. Klicka på **⚙️ Inställningar**
2. Klicka på **+ Skapa ny profil**
3. Ge profilen ett namn
4. Byt mellan profiler när du vill

### Logga träning
1. Välj träningspass (Push/Pull/Ben/Löpning)
2. Klicka på varje övning för att logga
3. Ange vikter och reps
4. Klicka **Spara träning**

### Planera kost
1. Byt till **Kost**-fliken
2. Välj måltider för varje dag
3. Bocka av när du ätit
4. Följ dina kalorier och protein

## 🛠️ Teknisk Info

- **Ingen installation** - Fungerar direkt i webbläsaren
- **PWA-redo** - Kan installeras som app på mobilen
- **Firebase Realtime Database** - För synkronisering
- **Ren HTML/CSS/JS** - Inga beroenden
- **Mobile-first design** - Optimerad för mobil

## 📁 Filstruktur

```
provigo/
├── index.html          # Huvudfilen (ProVigo_Firebase_Final.html)
├── icon.svg           # App-ikon
└── README.md          # Denna fil
```

## 🔐 Säkerhet

**För produktion bör du:**
1. Lägga till Firebase Authentication
2. Begränsa databasregler till autentiserade användare
3. Implementera användarspecifika datanoder

## 📝 Licens

Personligt projekt - Använd fritt!

## 👨‍💻 Utvecklare

Utvecklat av Patrik
