# 🌱 Greenhouse Operator — Trainingsomgeving

Interactieve trainings-omgeving voor service-monteurs op het **Connext**-klimaatcomputer- en **Operator**-platform. Volledig statisch, draait in elke browser, geen backend nodig.

> Gebouwd om monteurs vertrouwd te maken met de Operator-werkstroom voordat ze in een echte kas met een live regeling staan. Belangrijk omdat het tekort aan gekwalificeerde monteurs een wezenlijk risico vormt voor de tuinbouwsector.

## ✨ Functies

### Tweetraps-navigatie zoals Operator
- **Topbalk**: Home / Climate / Water / Energy / General met iconen
- **Witte zijbalk**: sub-modules per sectie (Climate heeft Dashboard, Ventilation, Heating, Curtain, CO₂ dosage, ... 18 items totaal)
- **Tab-strip**: tabs als Climate overview / Modulating light control / Climate visual / Strategies

### 🔍 Zoekfunctie voor monteurs (kerne-feature)
Het vergrootglas in de topbalk (of toets `/`) opent een zoek-dialoog die accepteert:
- **I-nummers** zoals `I120` (Ventilation Strategy), `I160` (Curtain), `I675` (Moisture)
- **Alarmcodes** zoals `154` (KasT te hoog), `600` (Boiler T te hoog), `10100` (Edge Gateway)
- **Onderwerpen** in Dutch + English: `scherm`, `recept`, `ventilatie`, `wkk`, ...

Resultaten worden gecategoriseerd weergegeven (`Climate > Ventilation > Strategy`) en navigeren bij klik direct naar de juiste pagina.

### 🏭 Climate Visual — 4 kassen in 2×2-grid
Elke kas heeft eigen pastel-tegels rond een SVG-illustratie: Lee, Wind, VentT, CO₂, GrhT, HeatT, RH, AH, Curtain, Position. Klik op een tegel om een widget-popup te openen met grafiek + huidige waarde + shortcuts.

Links een gemeenschappelijk Overzicht-paneel: Outside-T, RH, AH, HD, Dew Point, PAR sum today/yesterday, Sunrise/Sunset.

### 💡 Modulating Light Control
Volledige tabel met MOD. LIGHT 51-68: Strategy, Actual status, Channel 1-7 percentages, Des. light%, Des. steps, Recipe, Forced status, Limitation — met kleur-codering zoals in Operator.

### 💧 Recept-editor (Water)
Drill-down: Recipes-lijst → detail met COMPOSITION & ALARM LIMITS, DOSING CHANNEL RATIO (A-tank / B-tank / Acid), CALCULATED AND MEASURED.

### 📈 Strategieën
Period-tabellen met Period 1-6 kolommen voor ventilatie, verwarming, scherm. Black-out / Energy / Shading / Humidity / Side / Gap / Curtain control tabs per gewas.

### 🔥 Energy
Dashboard met Energy sources (Boilers 1-2, CHPs 1-3, Heat exchanger), CO₂ management, Buffer (10 sensoren), Manifold, Buffer-detail.

### 🌤 Weather + Alarmen
Weather-station met sensor-overlay op illustratie. Alarms-pagina met ack-functie en geschiedenis.

### 🔄 Live simulatie
Achtergrond-tick elke 2,5s update alle waarden: buiten-T volgt zonneboog, straling/PAR varieert, ramen reageren op T-stijging, CO₂ daalt door ventilatie en stijgt door dosering, ketel/pijp reageert op vraag. Triggert automatisch alarmen wanneer drempels worden overschreden.

## 🚀 Lokaal proberen

Geen build-stap, geen dependencies. Open simpelweg `index.html` in elke moderne browser.

```bash
# of een eenvoudige local server starten:
python3 -m http.server 8000
# open http://localhost:8000
```

## 📤 Deploy naar GitHub Pages

1. **Maak een nieuwe repository** aan op GitHub (bv. `operator-training`)
2. **Upload alle bestanden** uit deze map:
   ```
   index.html
   manifest.json
   README.md
   LICENSE
   docs/
     Trainingscurriculum.docx
   ```
   Via web-interface: "Add file" → "Upload files" → sleep alles erin → "Commit changes"

3. **Activeer GitHub Pages**:
   - Ga naar `Settings` → `Pages`
   - Onder "Source": kies branch `main` en folder `/ (root)`
   - Klik **Save**

4. **Wacht 1-2 minuten** — je app is live op:
   ```
   https://JOUW-GEBRUIKERSNAAM.github.io/operator-training/
   ```

Klaar! De URL kun je delen met je monteurs.

## 📦 Bestandsstructuur

```
.
├── index.html              # De volledige trainings-omgeving (HTML/CSS/JS in één bestand)
├── manifest.json           # PWA-manifest (installeerbaar als app)
├── README.md               # Deze documentatie
├── LICENSE                 # MIT licentie
├── .gitignore
└── docs/
    └── Trainingscurriculum.docx   # 10-modules curriculum (Word)
```

## 🎓 Curriculum

Het Word-bestand in `docs/` bevat het volledige trainings-curriculum (10 modules, ~80 contact-uur + 40 zelfstudie). Modules dekken Connext-hardware, sensoren, Operator-app, ventilatie, verwarming, scherm, CO₂, belichting, energie, water/fertigatie, alarmen-handling en service-procedures.

## 🛠 Technische details

- Eén HTML-bestand, geen build-systeem
- IBM Plex Sans + JetBrains Mono via Google Fonts (CDN)
- Vanilla JavaScript — geen frameworks
- PWA-installeerbaar via manifest.json
- Geen tracking, geen analytics, geen backend
- Werkt offline na initiële load (zodra Google Fonts gecachet zijn)

## 📜 Licentie

MIT — zie LICENSE.

## 🤝 Disclaimer

Dit is een **trainings-simulator**, geen echt regelsysteem. De Connext klimaatcomputer en Operator-applicatie zijn producten van Priva. Deze trainings-omgeving is niet door Priva gebouwd of geëndorsed; bedoeld puur als oefenmateriaal vóór monteurs in een echte installatie werken.

---

🌍 Voor een duurzame voedselvoorziening, met goed opgeleide monteurs.
