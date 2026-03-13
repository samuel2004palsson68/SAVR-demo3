# SAVR Aktieassistent – Demo

AI-driven aktieassistent inbyggd i SAVRs bolagssida. Byggd med React + Claude AI med webbsökning i realtid.

---

## 🚀 Deploya på Vercel (10 min)

### Steg 1 – Skaffa en Anthropic API-nyckel
1. Gå till [console.anthropic.com](https://console.anthropic.com)
2. Logga in / skapa konto
3. Gå till **API Keys** → **Create Key**
4. Kopiera nyckeln (börjar med `sk-ant-...`) – spara den säkert

### Steg 2 – Ladda upp koden till GitHub
1. Gå till [github.com](https://github.com) → logga in / skapa konto
2. Klicka **"New repository"** → döp den till `savr-demo` → **Create**
3. Ladda upp alla filer i denna zip (drag & drop i GitHubs UI)
4. Klicka **"Commit changes"**

### Steg 3 – Deploya på Vercel
1. Gå till [vercel.com](https://vercel.com) → **Sign up with GitHub**
2. Klicka **"Add New Project"**
3. Välj ditt `savr-demo` repo → klicka **Import**
4. Öppna **"Environment Variables"** innan du klickar Deploy:
   - **Name:** `ANTHROPIC_API_KEY`
   - **Value:** din nyckel från steg 1 (t.ex. `sk-ant-api03-...`)
   - Klicka **Add**
5. Klicka **Deploy** 🎉

Efter ~1 minut får du en länk som:
```
https://savr-demo.vercel.app
```

Dela denna länk med SAVR-teamet!

---

## 💻 Kör lokalt (valfritt)

Skapa en fil `.env` i projektets rotmapp:
```
ANTHROPIC_API_KEY=sk-ant-api03-din-nyckel-här
```

Installera och starta:
```bash
npm install
npm start
```

Öppna [http://localhost:3000](http://localhost:3000)

---

## 📁 Projektstruktur

```
savr-demo/
├── api/
│   └── chat.js          ← Vercel serverless proxy (håller API-nyckeln säker)
├── public/
│   └── index.html
├── src/
│   ├── index.js
│   └── App.js           ← Hela SAVR-komponenten
├── package.json
├── vercel.json
└── README.md
```

---

## 🔒 Säkerhet

API-nyckeln lagras **aldrig** i frontend-koden. Den lever enbart som miljövariabel i Vercel och används via serverless-proxyn `api/chat.js`. Användarna ser aldrig nyckeln.
