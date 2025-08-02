# Region Weather Alert System - Pre - ALPHA 0.1.3


A lightweight, configurable frontend alert display module that fetches and displays CAP-formatted MetService weather alerts for a specific geographic region (e.g. Far North District). This system integrates with GeoJSON boundaries, optional proxy usage, and a floating HTML alert interface for local government or public-facing websites.

## 🌦 Features

- ✅ Parses MetService CAP alerts
- 📍 Filters alerts to your district using GeoJSON and Turf.js
- 🎯 Highlights relevant, upcoming, and expired alerts
- 🧽 Optional proxy support for CORS-safe data fetching
- 🦨 Lightweight: No frameworks, just plain JavaScript

## 🔧 Files and Modules

| File                  | Purpose                                         |
|-----------------------|-------------------------------------------------|
| `index.html`          | Example HTML page with alert panel             |
| `alert.js`            | Main alert logic (fetch, filter, display)      |
| `map.js`              | GeoJSON loader and spatial intersection logic  |
| `config.js`           | System settings (feed URL, proxy toggle, etc)  |
| `style.css`           | Styles for alert cards and floating panel      |

## 📦 Installation

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/almokinsgov/Region-Weather-Alert-System.git
   cd region-weather-alerts
   ```

2. **Host the Files:**
   Drop the contents onto your preferred static site (e.g. local council website, CodePen, or web server).

3. **Configure Region:**
   - Update `config.js` with your CAP feed and proxy preferences
   - Replace the GeoJSON in `map.js` with your district or boundary

## ⚙️ Configuration

Edit `config.js` to control system behavior:

```js
const AlertConfig = {
  FEED_URL: "https://alerts.metservice.com/cap/atom",
  USE_PROXY: true,
  PROXY: "https://corsproxy.io/?",

  SHOW_EXPIRED_ALERTS: false,
  SHOW_NON_FAR_NORTH_ALERTS: true,
  REQUIRE_ONSET_WITHIN_WINDOW: true
};
```

## 🗏️ GeoJSON Support

Replace the sample polygon in `map.js` with your region’s coordinates. This enables spatial filtering using Turf.js to only show alerts relevant to your district.

## 🔒 Permissions

This tool reads from MetService’s [public CAP feed]([https://alerts.metservice.com/cap/atom](https://www.metservice.com/files/documents/cap/MetService%20CAP%20Feed%20User%20Guide%20v1.1.pdf)), which is licensed under Creative Commons BY 4.0.

## 🙌 Credits

Created by Amorangi Mathews for public alert transparency and local government usability. Built with:

- [MetService CAP Alerts](https://metservice.com)
- [Turf.js](https://turfjs.org) for spatial logic
- [Leaflet](https://leafletjs.com) for optional map visualisation


