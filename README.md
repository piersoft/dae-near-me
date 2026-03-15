# 💓 DAE Near Me

> **Trova il defibrillatore più vicino a te in pochi secondi.**  
> Web app mobile-first che mostra i defibrillatori (DAE) entro 2 km dalla tua posizione, con mappa interattiva e lista ordinata per distanza.

[![GitHub Pages](https://img.shields.io/badge/Live%20Demo-GitHub%20Pages-brightgreen?logo=github)](https://piersoft.github.io/dae-near-me/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![OpenStreetMap](https://img.shields.io/badge/Data-OpenStreetMap-blue?logo=openstreetmap)](https://www.openstreetmap.org/)

---

## 🖥️ Demo

👉 **[piersoft.github.io/dae-near-me](https://piersoft.github.io/dae-near-me/)**

---

## ✨ Funzionalità

- 📍 **Geolocalizzazione GPS** — rileva automaticamente la tua posizione
- 🗺️ **Mappa interattiva** (Leaflet + OpenStreetMap) con marker colorati
- 📋 **Lista ordinata** dal defibrillatore più vicino al più lontano
- 📏 **Distanza in tempo reale** calcolata con formula di Haversine
- 🏷️ **Tag informativi** — accesso pubblico, interno/esterno, h24, brand/operatore
- 🔗 **Navigazione diretta** — link a Google Maps per ogni dispositivo
- 📱 **Mobile-first** — ottimizzato per smartphone, funziona su qualsiasi browser moderno
- 🌐 **Dati aperti** — interroga il database globale di OpenStreetMap via Overpass API

---

## 🚀 Come si usa

1. Apri la **[demo live](https://piersoft.github.io/dae-near-me/)**
2. Premi il pulsante **"Trova DAE"**
3. Consenti l'accesso alla posizione GPS
4. Esplora la mappa e la lista dei defibrillatori vicini a te
5. Clicca su una card per centrare la mappa e ottenere indicazioni stradali

---

## 🛠️ Tecnologie

| Libreria | Uso |
|---|---|
| [Leaflet 1.9](https://leafletjs.com/) | Mappa interattiva |
| [OpenStreetMap](https://www.openstreetmap.org/) | Tiles cartografici |
| [Overpass API](https://overpass-api.de/) | Query `emergency=defibrillator` |
| [Google Fonts](https://fonts.google.com/) | DM Sans + Space Mono |
| Vanilla JS | Nessun framework, zero dipendenze NPM |

---

## 📡 API utilizzata

La query Overpass interroga tutti i nodi/way/relation con tag `emergency=defibrillator` in un bounding box di ~2 km attorno alla posizione:

```
[out:json][timeout:25];
nwr["emergency"="defibrillator"](bbox);
out geom;
```

Dati © [OpenStreetMap contributors](https://www.openstreetmap.org/copyright), licenza [ODbL](https://opendatacommons.org/licenses/odbl/).

---

## 🏃 Esegui in locale

Nessun build step — è un file HTML statico:

```bash
git clone https://github.com/piersoft/dae-near-me.git
cd dae-near-me
# apri index.html nel browser (per il GPS serve HTTPS o localhost)
python3 -m http.server 8080
# poi vai su http://localhost:8080
```

---

## 🤝 Contribuire

I dati sui defibrillatori vengono da OpenStreetMap. Se conosci un DAE non mappato, aggiungilo su [openstreetmap.org](https://www.openstreetmap.org/) — apparirà automaticamente nell'app!

Per bug o miglioramenti apri una [issue](https://github.com/piersoft/dae-near-me/issues) o una pull request.

---

## 📄 Licenza

MIT © [Piersoft](https://github.com/piersoft)
