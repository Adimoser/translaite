# TranslAIte

> **AI-gestützte Übersetzungs- und Korrekturplattform mit Git-basiertem Review-Workflow**
> *AI-powered translation and proofreading platform with a Git-style review workflow*

---

## 🇩🇪 Deutsch

### Was ist TranslAIte?

TranslAIte ist eine Open-Source-Plattform zum Übersetzen, Korrigieren und Verwalten von Texten und Medieninhalten — unterstützt durch lokale oder cloud-basierte KI.

Gedacht für kleine Teams, Freelancer und alle, die Übersetzungsprojekte strukturiert und nachvollziehbar abwickeln wollen — ähnlich wie Entwickler mit Git arbeiten.

### Funktionen

- **AI-Erstübersetzung** — automatische Übersetzung via lokalem Sprachmodell (Ollama) oder Cloud-API
- **Diff & Merge** — Korrekturen werden als Änderungen angezeigt, können reviewed und gemergt werden (wie Pull Requests in Git)
- **Medienverarbeitung** — Videos und Audiodateien werden automatisch transkribiert (via Whisper) und stehen dann als übersetzbarer Text zur Verfügung
- **Kollaboration** — mehrere Personen arbeiten gemeinsam an einem Projekt, mit Benutzeranmeldung und Rollenverwaltung
- **Lokaler Modus** — komplett offline betreibbar, keine Cloud-Abhängigkeit
- **Versionierung** — jede Übersetzung wird als Revision gespeichert, Änderungshistorie jederzeit einsehbar
- **Semantische Suche** *(Phase 3)* — ähnliche Inhalte werden über eine Graphdatenbank (Neo4j) vernetzt und durchsuchbar gemacht

### Schnellstart (lokal)

**Voraussetzungen:** [Docker](https://www.docker.com/get-started) und [Docker Compose](https://docs.docker.com/compose/) müssen installiert sein.

```bash
# Repository klonen
git clone https://github.com/translaite/translaite.git
cd translaite

# Konfiguration anlegen
cp .env.example .env

# Starten
docker compose up
```

Die Anwendung ist danach erreichbar unter: **http://localhost:3000**

Im lokalen Modus ist kein Login erforderlich. Die Daten werden lokal in einer SQLite-Datenbank gespeichert.

### Selbst hosten (Server)

Für den Einsatz mit mehreren Personen und Kollaboration:

```bash
cp .env.example .env
# In .env: MODE=server, Datenbankverbindung und AUTH_ENABLED=true setzen

docker compose -f docker-compose.prod.yml up -d
```

### Tech-Stack

| Komponente | Technologie |
|---|---|
| Frontend | Vue 3 + Vite |
| Backend | FastAPI (Python) |
| Datenbank (lokal) | SQLite |
| Datenbank (Server) | PostgreSQL |
| AI lokal | Ollama |
| Transkription | OpenAI Whisper (lokal) |
| Graphdatenbank | Neo4j *(Phase 3)* |
| Deployment | Docker Compose |

### Roadmap

- [x] Projektplanung & Architektur
- [ ] **Phase 1** — Texte laden, AI-Übersetzung, Diff/Merge, Login
- [ ] **Phase 2** — Video/Audio-Upload, Whisper-Transkription
- [ ] **Phase 3** — Neo4j-Graphsuche, semantische Ähnlichkeit
- [ ] **Phase 4** — Live-Audio-Übersetzung (Echtzeit)

### Mitmachen

Beiträge sind willkommen! Bitte lies zuerst [CONTRIBUTING.md](CONTRIBUTING.md).

1. Repository forken
2. Feature-Branch erstellen (`git checkout -b feature/mein-feature`)
3. Änderungen committen (`git commit -m 'feat: mein feature'`)
4. Branch pushen (`git push origin feature/mein-feature`)
5. Pull Request öffnen

### Lizenz

MIT — frei nutzbar, veränderbar und weitergebbar. Siehe [LICENSE](LICENSE).

---

## 🇬🇧 English

### What is TranslAIte?

TranslAIte is an open-source platform for translating, proofreading, and managing text and media content — powered by local or cloud-based AI.

Built for small teams, freelancers, and anyone who wants to handle translation projects in a structured, traceable way — similar to how developers work with Git.

### Features

- **AI-assisted translation** — automatic first-pass translation via local language model (Ollama) or cloud API
- **Diff & Merge** — corrections are displayed as tracked changes that can be reviewed and merged (like pull requests in Git)
- **Media processing** — videos and audio files are automatically transcribed (via Whisper) and made available as translatable text
- **Collaboration** — multiple people work together on a project, with user authentication and role management
- **Local mode** — fully offline capable, no cloud dependency required
- **Versioning** — every translation is saved as a revision, with full change history at any time
- **Semantic search** *(Phase 3)* — similar content is connected and searchable via a graph database (Neo4j)

### Quick Start (local)

**Requirements:** [Docker](https://www.docker.com/get-started) and [Docker Compose](https://docs.docker.com/compose/) must be installed.

```bash
# Clone the repository
git clone https://github.com/translaite/translaite.git
cd translaite

# Create configuration
cp .env.example .env

# Start
docker compose up
```

The application will be available at: **http://localhost:3000**

In local mode, no login is required. Data is stored locally in a SQLite database.

### Self-hosting (Server)

For multi-user collaboration on a server:

```bash
cp .env.example .env
# In .env: set MODE=server, database connection, and AUTH_ENABLED=true

docker compose -f docker-compose.prod.yml up -d
```

### Tech Stack

| Component | Technology |
|---|---|
| Frontend | Vue 3 + Vite |
| Backend | FastAPI (Python) |
| Database (local) | SQLite |
| Database (server) | PostgreSQL |
| AI (local) | Ollama |
| Transcription | OpenAI Whisper (local) |
| Graph database | Neo4j *(Phase 3)* |
| Deployment | Docker Compose |

### Roadmap

- [x] Project planning & architecture
- [ ] **Phase 1** — Load texts, AI translation, diff/merge, login
- [ ] **Phase 2** — Video/audio upload, Whisper transcription
- [ ] **Phase 3** — Neo4j graph search, semantic similarity
- [ ] **Phase 4** — Live audio translation (real-time)

### Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) first.

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/my-feature`)
3. Commit your changes (`git commit -m 'feat: my feature'`)
4. Push the branch (`git push origin feature/my-feature`)
5. Open a pull request

### License

MIT — free to use, modify, and distribute. See [LICENSE](LICENSE).

---

<p align="center">
  Made with curiosity · Open Source · MIT License
</p>
