# Travel Innovation Atlas

An interactive 3D globe visualising **127 travel & tourism startups** across 50 countries and 6 continents — built in the style of the UN Tourism data platform.

Each marker represents a company using AI, blockchain, IoT, AR/VR or other emerging technology to reshape the global tourism industry.

---

## Features

- **3D rotating globe** powered by ArcGIS JavaScript API (SceneView)
- **127 companies** spanning AI booking, eco-tourism, hospitality tech, fintech, XR experiences and more
- **7 colour-coded categories** with an interactive filter — click any category in the legend to show only those markers
- **Draggable info card** on hover — shows the company's technology, how they use AI, global impact, SDG alignment and a link to their website
- **Zoom-aware rotation** — globe slows automatically when zoomed in; pauses on hover, resumes on mouse-out
- All company data stored in a single external `travel-innovations.geojson` file — easy to extend

---

## Categories

| Colour | Category |
|---|---|
| 🔵 Blue | AI-Powered Booking |
| 🟠 Orange | Experiences & Activities |
| 🔴 Red | Accommodation & Hospitality |
| 🟣 Purple | Travel Tech Infrastructure |
| 🟡 Yellow | Regional Travel Platforms |
| 💙 Cornflower | Identity & Connectivity |
| 🟢 Green | Eco & Conservation Tourism |

---

## Coverage

**Americas** — Chile, Argentina, Colombia, Peru, Brazil, Mexico, Costa Rica, Bolivia, Ecuador, Panama, Canada, USA

**Africa** — Kenya, South Africa, Nigeria, Uganda, Rwanda, Tanzania, Ghana, Namibia, Mozambique, Botswana, Ethiopia, Mauritius, Morocco, Zimbabwe

**Europe** — UK, France, Germany, Netherlands, Spain, Italy, Czech Republic

**Middle East** — UAE, Saudi Arabia, Kuwait

**Asia-Pacific** — China, India, Indonesia, Singapore, South Korea, Japan, Hong Kong, Taiwan, Thailand, Vietnam, Malaysia, Australia

**Central Asia** — Uzbekistan, Turkey

---

## Tech Stack

- [ArcGIS JavaScript API 4.22](https://developers.arcgis.com/javascript/) — SceneView, GeoJSONLayer, unique-value renderer
- Vanilla JS — draggable card, rotation loop, category filter
- GeoJSON — all 127 company records with coordinates, descriptions and metadata

---

## Running Locally

The GeoJSONLayer loads from a relative path (`./travel-innovations.geojson`), so the project must be served over HTTP — opening `index.html` directly as a file will not work.

```bash
# Python
python3 -m http.server 8000

# Node
npx serve .
```

Then open `http://localhost:8000`.

---

## Data Structure

Each feature in `travel-innovations.geojson` follows this schema:

```json
{
  "type": "Feature",
  "properties": {
    "name": "Airalo",
    "category": "Identity & Connectivity",
    "city": "Singapore",
    "country": "Singapore",
    "founded": 2019,
    "technology": "World's First eSIM Marketplace",
    "innovation": "How they use the technology...",
    "impact": "Measurable outcomes...",
    "sdg": "SDG 9 · Industry, Innovation & Infrastructure",
    "website": "airalo.com"
  },
  "geometry": {
    "type": "Point",
    "coordinates": [103.819, 1.352]
  }
}
```

To add a new company, append a feature to the array in `travel-innovations.geojson` and refresh.

---

## License

[MIT](./LICENSE)
