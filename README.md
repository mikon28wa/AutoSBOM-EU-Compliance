# AutoSBOM-EU-Compliance

> **Automatisierter SBOM-Generator mit Fokus auf EU-Compliance – Entwickelt für regulierte Umgebungen und sichere Lieferketten.**

---

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Status](https://img.shields.io/badge/Status-Actively%20Developing-blue)

---

## ✨ Features

### **Kernfunktionen**
- **Automatisierte SBOM-Generierung**: Scannt Quellcode (JS/TS, Python, Java, Go, Rust, etc.), Binärdateien, Docker-Container und Kubernetes-Manifeste.
- **Abhängigkeitserkennung**: Erfasst direkte und transitive Abhängigkeiten inkl. Lizenzen.
- **Unterstützte Standards**: **SPDX 3.0.1**, **CycloneDX 1.6**, SWID-Tags.
- **Exportformate**: JSON, XML, HTML (visualisiert), PDF.
- **Nested SBOMs**: SBOM-in-SBOM für komplexe Lieferketten.
- **CLI & REST API**: Für CI/CD-Pipelines und Automatisierung.
- **Strikte Trennung von SBOM und VEX/CSAF**.

### **EU-Compliance-Fokus**
- **Cyber Resilience Act (CRA)** – Artikel 10 (verpflichtend ab 2027).
- **ISO/IEC 5962:2021** – Internationaler SBOM-Standard.
- **BSI TR-03183-2** – Technische Richtlinien inkl. kryptografischer Hashes (SHA-256).
- **DSGVO-konform**: EU-Datenzentren zuerst, keine Abhängigkeit von US-Clouds.

---

## 🚀 Schnellstart

### **Voraussetzungen**
- [Node.js](https://nodejs.org/) (>= 20.x)
- [npm](https://www.npmjs.com/) oder [yarn](https://yarnpkg.com/)
- **Optional**: Docker (für Container-Scans)

---

### **Installation**

1. **Repository klonen:**
   ```bash
   git clone https://github.com/mikon28wa/AutoSBOM-EU-Compliance.git
   cd AutoSBOM-EU-Compliance
   ```

2. **Abhängigkeiten installieren:**
   ```bash
   npm install
   ```

3. **Umgebungsvariablen konfigurieren (falls benötigt):**
   - Erstelle eine `.env`-Datei:
     ```bash
     touch .env
     ```
   - Beispielkonfiguration:
     ```env
     # Optional: API-Keys für erweiterte Funktionen
     GITHUB_TOKEN=dein_github_token_hier
     ```

4. **CLI verwenden:**
   ```bash
   npx auto-sbom scan --dir ./path/to/project --output sbom.json
   ```

5. **REST API starten (falls vorhanden):**
   ```bash
   npm run start:api
   ```
   → API läuft unter `http://localhost:3000`.

---

## 📂 Projektstruktur

```
AutoSBOM-EU-Compliance/
├── src/
│   ├── cli/                  # CLI-Befehle
│   ├── core/                 # Kernlogik (SBOM-Generierung)
│   ├── api/                  # REST API (falls vorhanden)
│   ├── utils/                # Hilfsfunktionen
│   └── types/                # TypeScript-Typdefinitionen
├── config/                  # Konfigurationsdateien
├── tests/                   # Unit- und Integrationstests
├── .env.example              # Beispiel für Umgebungsvariablen
├── package.json
├── tsconfig.json
└── README.md
```

---

## 📡 API-Endpunkte (falls vorhanden)

| Endpunkt               | Methode | Beschreibung                          |
|------------------------|---------|--------------------------------------|
| `/api/sbom/generate`   | POST    | SBOM für ein Projekt generieren       |
| `/api/sbom/validate`   | POST    | SBOM auf Compliance prüfen           |
| `/api/sbom/export`     | POST    | SBOM in ein bestimmtes Format exportieren |

---

## 🛠 Technologien

| Bereich       | Technologie                     |
|---------------|---------------------------------|
| **Sprachen**  | TypeScript, Python (für Skripte) |
| **Frameworks**| Node.js, Express (für API)      |
| **SBOM-Tools**| Syft, Grype (integriert)         |
| **Build-Tool**| npm, TypeScript Compiler         |

---

## 🔍 Beispielnutzung

### **CLI-Befehl zum Scannen eines Projekts**
```bash
npx auto-sbom scan --dir ./my-project --format spdx --output sbom.spdx.json
```

### **API-Aufruf zur SBOM-Generierung**
```bash
curl -X POST http://localhost:3000/api/sbom/generate \
  -H "Content-Type: application/json" \
  -d '{"directory": "./my-project", "format": "cyclonedx"}'
```

---

## 🤝 Mitwirken

1. **Fork** das Repository.
2. **Branch** erstellen (`git checkout -b feature/neue-funktion`).
3. **Änderungen** commiten (`git commit -m "Füge neue Funktion hinzu"`).
4. **Push** (`git push origin feature/neue-funktion`).
5. **Pull Request** erstellen.

---

## 📄 Lizenz

Dieses Projekt steht unter der **MIT-Lizenz** – siehe [LICENSE](LICENSE) für Details.

---

## 📞 Unterstützung

- **Issues**: [GitHub Issues](https://github.com/mikon28wa/AutoSBOM-EU-Compliance/issues)
- **Autor**: [Michael Konradi](https://github.com/mikon28wa)
- **E-Mail**: [hallo@llmbluetools.de](mailto:hallo@llmbluetools.de)

---

## 🏆 Open-Core-Modell

- **Community Edition** (Open Source, MIT): Kern-Scanner, CLI, Basis-Standards & Compliance.
- **Premium Edition** (geplant): Web-UI, erweiterte VEX/CSAF-Automatisierung, Enterprise-Integrationen, gehostete Version & Support.