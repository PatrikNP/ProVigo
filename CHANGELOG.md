# Changelog - ProVigo Firebase Version

## Firebase-migration (2026-01-19)

### ✅ Nya funktioner
- Firebase Realtime Database integration
- Automatisk synkning mellan enheter
- Real-time datauppdateringar
- Cloud-baserad datalagring

### 🔄 Ändringar från localStorage-version

#### Data Storage
- **Tidigare:** localStorage (lokal lagring per enhet)
- **Nu:** Firebase Realtime Database (cloud-synkning)

#### Profil-system
- **Tidigare:** Multipla profiler med localStorage
- **Nu:** Förenklat till en profil per Firebase-användare
- **Anledning:** Enklare implementation, kan utökas med autentisering senare

#### Funktioner som behållits 100%
✅ Alla träningsprogram (Push/Pull/Legs/Löpning)
✅ Detaljerad övningsloggning
✅ Träningshistorik och statistik
✅ Kalendervy
✅ Viktuppföljning med grafer
✅ Midjemått-spårning
✅ Komplett måltidsplanering (10+ alternativ per måltid)
✅ Kalori- och proteinräkning
✅ Snacks-loggning
✅ Handlingslista
✅ Export/Import data
✅ Kroppsviktsinställningar
✅ Alla UI-funktioner

#### Funktioner som ändrats
- **Profil-hantering:** Skapa/byta/radera profiler inaktiverat (kan återaktiveras med Firebase Authentication)
- **UI-state (expandedDays):** Behålls i localStorage (lokalt per enhet)

### 📁 Firebase Data Structure

```
users/
  └── {userId}/                    (t.ex. "patrik")
      ├── workoutLog              → Alla träningspass
      ├── workoutHistory          → Träningshistorik
      ├── userSettings            → Användarinställningar (kroppsvikt etc)
      ├── weightLog               → Viktuppföljning
      ├── eatenMeals              → Ätna måltider per dag
      ├── dailySnacks             → Snacks per dag
      ├── mealSelections          → Valda måltider för veckan
      └── mealAlternatives        → Anpassade måltidsalternativ
```

### 🔧 Tekniska förbättringar
- Async/await för alla Firebase-operationer
- Error handling för nätverksfel
- Automatisk återanslutning vid nätverksavbrott
- Optimerad datainläsning vid app-start

### 🔐 Säkerhet
- **Nuvarande:** Öppna regler för enkel testning
- **Rekommendation:** Lägg till Firebase Authentication för produktion

### 📱 Kompatibilitet
- ✅ Fungerar på alla moderna webbläsare
- ✅ Fungerar på mobil och desktop
- ✅ Responsiv design behållen
- ✅ Offline-funktionalitet (Firebase cachar data lokalt)

### 🐛 Kända begränsningar
- Ingen multi-user support (kan läggas till med Authentication)
- Kräver internet för första synkning
- UI-state (t.ex. vilka dagar som är expanderade) synkas inte mellan enheter

### 🚀 Framtida förbättringar
- [ ] Firebase Authentication för säker multi-user support
- [ ] Offline-first med bättre caching
- [ ] Real-time uppdateringar mellan enheter
- [ ] Dela kostplaner mellan familjemedlemmar
- [ ] Push-notifikationer för träningspåminnelser

---

**Version:** Firebase v1.0
**Datum:** 2026-01-19
**Utvecklare:** Patrik
