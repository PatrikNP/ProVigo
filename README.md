# ProVigo - Tränings & Kost App

En komplett tränings- och kostapp med Firebase-synkning mellan enheter.

## 🎯 Funktioner

### 💪 Träning
- Push/Pull/Legs/Löpning träningsprogram
- Detaljerad övningsloggning med vikter och repetitioner
- Träningshistorik och statistik
- Kalendervy med träningar
- Viktuppföljning med grafer

### 🍽️ Kost
- Måltidsplanering för hela veckan
- 10+ alternativ för varje måltid (frukost, lunch, middag, kvällsmål, snacks)
- Automatisk kalori- och proteinräkning
- Bocka av ätna måltider
- Handlingslista
- Spåra tidigare dagar

### 📊 Uppföljning
- Viktutveckling med grafer
- Midjemått-spårning
- Kalorispårning (intag vs förbränning)
- Proteinmål

## 🚀 Installation

### 1. Ladda ner filen
Ladda ner `ProVigo_Firebase_Complete.html` från detta repository.

### 2. Firebase Setup

#### A. Skapa Firebase-projekt (om du inte har ett)
1. Gå till [Firebase Console](https://console.firebase.google.com/)
2. Klicka "Add project" eller använd befintligt projekt
3. Följ instruktionerna

#### B. Aktivera Realtime Database
1. I Firebase Console, gå till **Realtime Database**
2. Klicka **"Create Database"**
3. Välj **"europe-west1"** som location
4. Välj **"Start in test mode"**

#### C. Konfigurera Security Rules
1. Gå till **Realtime Database → Rules**
2. Ersätt med följande regler:

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

3. Klicka **"Publish"**

⚠️ **OBS:** Dessa regler är öppna för testning. För produktion, använd autentisering.

#### D. Hämta din Firebase-konfiguration
1. I Firebase Console, gå till **Project Settings** (kugghjulet)
2. Scrolla ner till "Your apps"
3. Klicka på **Web** (</>)
4. Kopiera firebaseConfig-objektet

#### E. Uppdatera konfigurationen i filen
Öppna `ProVigo_Firebase_Complete.html` och hitta detta (rad ~924):

```javascript
const firebaseConfig = {
    apiKey: "DIN-API-KEY",
    authDomain: "ditt-projekt.firebaseapp.com",
    databaseURL: "https://ditt-projekt.firebasedatabase.app",
    projectId: "ditt-projekt",
    storageBucket: "ditt-projekt.appspot.com",
    messagingSenderId: "123456789",
    appId: "1:123456789:web:abc123"
};
```

Ersätt med din egen konfiguration.

### 3. Ändra användar-ID (valfritt)
Om du vill ändra från "patrik" till ditt eget namn, hitta denna rad (rad ~937):

```javascript
const userId = 'patrik'; // Ändra till ditt namn
```

### 4. Öppna appen
- Dubbelklicka på `ProVigo_Firebase_Complete.html`
- Eller öppna via en webbserver (rekommenderat för bästa kompatibilitet)

## 📱 Synka mellan enheter

1. Ladda upp filen till en webbserver (GitHub Pages, Netlify, etc.)
2. Öppna samma URL på alla dina enheter
3. All data synkar automatiskt via Firebase!

### Alternativ: Använd lokalt på flera enheter
1. Kopiera filen till varje enhet
2. Se till att alla använder samma Firebase-konfiguration
3. Data synkar automatiskt

## 🔧 Teknisk information

### Byggd med:
- Vanilla JavaScript (inga ramverk)
- Firebase Realtime Database
- HTML5 & CSS3
- Responsiv design

### Firebase-struktur:
```
users/
  └── {userId}/
      ├── workoutLog
      ├── workoutHistory
      ├── userSettings
      ├── weightLog
      ├── eatenMeals
      ├── dailySnacks
      ├── mealSelections
      └── mealAlternatives
```

## 🔐 Säkerhet (för produktion)

För en produktions-app, använd Firebase Authentication och dessa säkrare regler:

```json
{
  "rules": {
    "users": {
      "$userId": {
        ".read": "auth != null && auth.uid == $userId",
        ".write": "auth != null && auth.uid == $userId"
      }
    }
  }
}
```

## 📝 Licens

Fri att använda för personligt bruk.

## 🐛 Problem?

Om du stöter på problem:
1. Öppna Developer Console (F12)
2. Kolla Console-fliken för felmeddelanden
3. Verifiera att Firebase-reglerna är publicerade
4. Kontrollera att Firebase-konfigurationen är korrekt

## 👨‍💻 Utvecklare

Skapad för personlig användning med Firebase-synkning.

---

**Lycka till med din träning och kost! 💪🍽️**
