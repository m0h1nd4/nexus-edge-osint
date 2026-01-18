# Nexus Edge OSINT

**Mobile-First OSINT Data Collection Tool with Cyberpunk UI**

A professional Open Source Intelligence (OSINT) data collection tool designed for field operations. Capture entities, relationships, and metadata directly from your mobile device and export desktop-compatible CSV files for graph database analysis.

![Version](https://img.shields.io/badge/version-7.0-00f0ff.svg?style=flat-square)
![License](https://img.shields.io/badge/license-MIT-fcee0a.svg?style=flat-square)
![Platform](https://img.shields.io/badge/platform-web-ff003c.svg?style=flat-square)
![No Backend](https://img.shields.io/badge/backend-none-050505.svg?style=flat-square)

---

## Version History

### v7.0 (Current)
- Complete UI overhaul with dynamic form fields
- Extended data model: 47 fields (up from 5)
- Entity-specific fields (Person, Organization, Vehicle)
- Collapsible sections for mobile optimization
- 12 social media platforms supported
- Full address and contact data capture
- Backward-compatible CSV import (v6.x format supported)
- Search functionality in database view
- Scroll-to-top button
- Form validation with visual feedback
- UTF-8 BOM for Excel compatibility

### v6.1
- CSV sync and merge functionality
- Custom export filename configuration
- Duplicate detection and deduplication tool
- Native sharing via Web Share API
- Cyberpunk UI design (neon theme)

### v6.0
- Initial public release
- Basic entity capture (5 fields)
- localStorage persistence
- CSV import/export

---

## Overview

**Nexus Edge** enables structured OSINT data collection during live research operations. The tool runs entirely client-side in modern browsers, requires no backend infrastructure, and stores data persistently using localStorage.

Output format is optimized for import into graph databases like **Neo4j** and compatible with the NightCity OSINT Desktop application.

### Key Capabilities

- Capture entities (persons, organizations, vehicles, locations)
- Define relationships between nodes
- Store comprehensive metadata (contact, address, social media)
- Export standardized 47-column CSV files
- Synchronize data between mobile and desktop

---

## Features

### Data Collection

| Category | Fields |
|----------|--------|
| **Core** | Name, Type, Relationship, Source |
| **Person** | Birth date, Gender, Height, Hair/Eye color, Nationality, Distinctive features |
| **Organization** | Founding date, Legal form, Registration number, Industry, Website, Employee count |
| **Vehicle** | License plate, Make, Model, Color, Year, VIN |
| **Address** | Street, House number, Extra, Postal code, City, Country |
| **Contact** | Phone, Mobile, Fax, Email |
| **Social Media** | Facebook, Instagram, TikTok, Twitter/X, LinkedIn, XING, YouTube, Telegram, WhatsApp, Signal, Snapchat, Discord |
| **Meta** | Information source, Notes |

### Entity Types

```
Person | Firma | Verein | Organisation | Partei | Club | Location | Fahrzeug | Objekt
```

### Relationship Types

```
MEMBER_OF      FRIEND_OF       WORKS_AT        OWNER_OF        FAMILY
SEEN_AT        SUSPECT         DIRECTOR_OF     SUBSIDIARY_OF   INVESTED_IN
CONTRACTED_BY  REGISTERED_AT   ALIAS_OF        AFFILIATED_WITH LIVES_AT
MARRIED_TO     CHILD_OF        PARENT_OF       SIBLING_OF
```

### Technical Features

- **Offline-capable**: No internet connection required after initial load
- **Persistent storage**: Data survives browser restarts via localStorage
- **Duplicate detection**: Prevents accidental duplicate entries
- **Dynamic forms**: Fields adapt based on selected entity type
- **Collapsible sections**: Optimized for small screens
- **Search & filter**: Quick lookup in database view
- **Native sharing**: Share CSV via system share sheet (HTTPS required)
- **Backward compatible**: Imports both old (5-column) and new (47-column) CSV formats
- **UTF-8 with BOM**: Excel-compatible encoding

---

## Installation

No installation required. The tool consists of a single HTML file.

### Option 1: Direct Use
1. Download `nexus-edge.html`
2. Open in any modern browser (Chrome, Firefox, Safari, Edge)

### Option 2: Local Server
```bash
# Clone repository
git clone https://github.com/m0h1nd4/nexus-edge-osint.git
cd nexus-edge-osint

# Serve locally (enables sharing features)
npx serve .
# or
python -m http.server 8080
```

### Option 3: Host on HTTPS
For native sharing functionality, host the file on any HTTPS-enabled server or use GitHub Pages.

---

## Usage

### Workflow

```
┌─────────┐    ┌──────────┐    ┌────────┐
│  INPUT  │ -> │ DATABASE │ -> │ EXPORT │
└─────────┘    └──────────┘    └────────┘
```

1. **INPUT**: Enter entity data. Required fields are highlighted.
2. **SAVE**: Click `>> SAVE TO MEMORY <<`. Duplicates are automatically detected.
3. **DATABASE**: Review, edit, or delete entries. Use search to filter.
4. **EXPORT**: Download or share CSV file.

### CSV Format

The export follows a standardized 47-column format:

```csv
name,type,relation,source,street,house_number,address_extra,postal_code,city,country,phone,mobile,fax,email,birth_date,gender,height_cm,hair_color,eye_color,nationality,distinctive_features,founding_date,registration_number,industry,website,employee_count,legal_form,license_plate,vehicle_make,vehicle_model,vehicle_color,vehicle_year,vin,facebook,instagram,tiktok,twitter,linkedin,xing,youtube,telegram,whatsapp,signal,snapchat,discord,info_source,notes
```

### Data Migration

When importing older CSV files (5-column format), the tool automatically:
- Maps `identifier` field to `license_plate` (for vehicles) or `info_source` (for other types)
- Preserves all existing data
- Applies default values where needed

---

## Technology Stack

| Component | Technology |
|-----------|------------|
| Frontend | HTML5, CSS3 (Grid/Flexbox) |
| Logic | Vanilla JavaScript (ES6+) |
| Storage | Web Storage API (localStorage) |
| Sharing | Web Share API |
| Styling | CSS Custom Properties |

**No external dependencies. No build step. No framework.**

---

## Browser Support

| Browser | Version | Status |
|---------|---------|--------|
| Chrome | 80+ | Full support |
| Firefox | 75+ | Full support |
| Safari | 13+ | Full support |
| Edge | 80+ | Full support |
| Mobile Chrome | 80+ | Full support |
| Mobile Safari | 13+ | Full support |

---

## Project Structure

```
nexus-edge-osint/
├── nexus-edge.html    # Main application (single-file)
├── README.md          # Documentation
├── LICENSE            # MIT License
└── .gitignore         # Git ignore rules
```

---

## Security Considerations

- All data is stored locally in your browser
- No data is transmitted to external servers
- Clear browser data to remove all stored information
- Use private/incognito mode for sensitive operations
- For production use, consider additional encryption

---

## Roadmap

- [ ] IndexedDB support for larger datasets
- [ ] Data encryption at rest
- [ ] Multiple database profiles
- [ ] Direct Neo4j export
- [ ] PWA support with service worker
- [ ] Collaborative sync via WebRTC

---

## Contributing

Contributions are welcome. Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit your changes (`git commit -m 'Add new feature'`)
4. Push to the branch (`git push origin feature/new-feature`)
5. Open a Pull Request

---

## License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

## Author

**m0h1nd4**

---

<p align="center">
  <sub>Built for the shadows. Designed for the edge.</sub>
</p>
