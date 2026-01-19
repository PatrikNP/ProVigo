# ProVigo - Komplett Installationsguide

## 📋 Översikt
Denna guide hjälper dig att sätta upp ProVigo med Firebase från början.

## ⏱️ Uppskattad tid: 10-15 minuter

---

## Steg 1: Firebase Console Setup

### 1.1 Logga in på Firebase
1. Gå till https://console.firebase.google.com/
2. Logga in med ditt Google-konto

### 1.2 Välj/Skapa projekt
**Om du REDAN har ett Firebase-projekt (t.ex. patrikapps-cd169):**
- Klicka på projektet i listan

**Om du INTE har ett projekt än:**
1. Klicka "Add project"
2. Ge projektet ett namn (t.ex. "ProVigo" eller "MinTräningsapp")
3. Acceptera villkoren
4. Klicka "Continue"
5. Google Analytics kan vara avstängt (du behöver det inte)
6. Klicka "Create project"
7. Vänta ~30 sekunder
8. Klicka "Continue"

---

## Steg 2: Skapa Realtime Database

### 2.1 Navigera till Realtime Database
1. I vänstermenyn, klicka på **"Realtime Database"** (under Build)
2. Klicka på den blå knappen **"Create Database"**

### 2.2 Välj inställningar
1. **Database location:** Välj **"europe-west1"** (eller närmaste region)
2. Klicka "Next"
3. **Security rules:** Välj **"Start in test mode"** 
4. Klicka "Enable"
5. Vänta några sekunder medan databasen skapas

---

## Steg 3: Konfigurera Security Rules

### 3.1 Öppna Rules
1. Du är nu i Realtime Database-vyn
2. Klicka på fliken **"Rules"** (bredvid "Data")

### 3.2 Ändra reglerna
Du ser något liknande:
```json
{
  "rules": {
    ".read": "now < 1745654400000",
    ".write": "now < 1745654400000"
  }
}
```

**Ta bort ALLT** och ersätt med:
```json
{
  "rules": {
    "users": {
      "$userId": {
        ".read": true,
        ".write": true
      }
    }
  }
}
```

### 3.3 Publicera
1. Klicka på den blå knappen **"Publish"** uppe till höger
2. Om du får en varning om säkerhet, klicka "Publish anyway"
3. ✅ Du ska nu se "Rules published successfully" eller liknande

---

## Steg 4: Hämta Firebase-konfiguration

### 4.1 Gå till Project Settings
1. Klicka på **kugghjulet** ⚙️ bredvid "Project Overview" (längst upp i vänstermenyn)
2. Välj **"Project settings"**

### 4.2 Hitta din Web App Config
1. Scrolla ner till **"Your apps"**
2. Om du redan har en webb-app, se konfigurationen där
3. Om INTE, klicka på **"</>"** (Web-ikonen) för att skapa en

### 4.3 Registrera appen (om ny)
1. Ge appen ett smeknamn (t.ex. "ProVigo")
2. **BOCKA INTE I** "Also set up Firebase Hosting"
3. Klicka **"Register app"**

### 4.4 Kopiera konfigurationen
Du ser nu kod som:
```javascript
const firebaseConfig = {
  apiKey: "AIzaSyXxXxXxXxXxXxXxXxXxXxXxXxXxXxX",
  authDomain: "ditt-projekt-123.firebaseapp.com",
  databaseURL: "https://ditt-projekt-123-default-rtdb.europe-west1.firebasedatabase.app",
  projectId: "ditt-projekt-123",
  storageBucket: "ditt-projekt-123.appspot.com",
  messagingSenderId: "123456789012",
  appId: "1:123456789012:web:abc123def456"
};
```

**KOPIERA HELA DETTA OBJEKT!** Du behöver det i nästa steg.

---

## Steg 5: Uppdatera ProVigo-filen

### 5.1 Öppna filen i en texteditor
1. Högerklicka på **ProVigo_Firebase_Complete.html**
2. Välj "Öppna med" → **Notepad** (Windows) eller **TextEdit** (Mac) eller **VS Code**

### 5.2 Hitta Firebase-konfigurationen
1. Tryck **Ctrl+F** (eller Cmd+F på Mac)
2. Sök efter: `const firebaseConfig`
3. Du hamnar runt rad 924-933

### 5.3 Ersätt konfigurationen
Du ser:
```javascript
const firebaseConfig = {
    apiKey: "AIzaSyCZjOBDcyyLMQZDeQPKK0bpdRSh3prLs0M",
    authDomain: "patrikapps-cd169.firebaseapp.com",
    databaseURL: "https://patrikapps-cd169-default-rtdb.europe-west1.firebasedatabase.app",
    projectId: "patrikapps-cd169",
    storageBucket: "patrikapps-cd169.firebasestorage.app",
    messagingSenderId: "334803684499",
    appId: "1:334803684499:web:13c0f00c357ad5c97ed166"
};
```

**Ersätt med DIN konfiguration** från Firebase Console!

### 5.4 Ändra användar-ID (valfritt)
1. Hitta raden: `const userId = 'patrik';` (runt rad 937)
2. Ändra till ditt namn, t.ex.: `const userId = 'sofie';`

### 5.5 Spara filen
1. Tryck **Ctrl+S** (eller Cmd+S på Mac)
2. Stäng texteditorn

---

## Steg 6: Testa appen

### 6.1 Öppna appen
1. Dubbelklicka på **ProVigo_Firebase_Complete.html**
2. Den öppnas i din webbläsare

### 6.2 Lägg till testdata
1. Klicka på "💪 Push" för att starta ett träningspass
2. Klicka "✓ Slutför träning"
3. Gå till fliken "🍽️ Kost"
4. Bocka av en måltid

### 6.3 Verifiera i Firebase
1. Gå tillbaka till Firebase Console
2. Realtime Database → **Data**-fliken
3. Du ska nu se:
```
din-databas
└── users
    └── patrik (eller ditt namn)
        ├── workoutLog
        ├── eatenMeals
        └── ...
```

✅ **Om du ser data här - FUNGERAR DET!** 🎉

---

## Steg 7: Testa synkning (valfritt)

### 7.1 På samma enhet
1. Stäng webbläsaren helt
2. Öppna appen igen
3. Din data ska finnas kvar!

### 7.2 På annan enhet
1. Kopiera **ProVigo_Firebase_Complete.html** till din mobil/annan dator
2. Öppna filen
3. Samma data visas! 🎊

---

## ❓ Felsökning

### Problem: "Sidan är tom"
**Lösning:** Öppna Developer Console (F12) och kolla felmeddelanden

### Problem: "Data sparas inte"
**Lösning:** 
1. Kontrollera att du publicerat Rules i Firebase
2. Kolla att firebaseConfig är korrekt kopierad
3. Titta i Console (F12) efter felmeddelanden

### Problem: "Firebase is not defined"
**Lösning:** Filen måste öppnas via http:// inte file://
- Alternativ 1: Använd en lokal webbserver
- Alternativ 2: Ladda upp till GitHub Pages eller Netlify

### Problem: "Permission denied"
**Lösning:** 
1. Gå till Firebase Console → Realtime Database → Rules
2. Verifiera att reglerna är korrekta
3. Klicka "Publish" igen

---

## 🎯 Klart!

Du har nu en fullt fungerande ProVigo-app med Firebase-synkning!

**Nästa steg:**
- Börja logga dina träningspass
- Planera din kostvecka
- Följ din viktuppföljning
- Synka mellan alla dina enheter!

**Lycka till! 💪🍽️**
