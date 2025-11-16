# 🌟 Astrea Note

<div align="center">
  <img src="[Logo Placeholder URL]" alt="Logo Astrea Note: simbolo astratto minimalista che suggerisce flusso finanziario e ordine, reso in bianco su sfondo blu." width="200"/>
  <h1>Astrea Note</h1>
  <p>Software Open Source per la gestione delle note spese aziendali</p>
</div>

| GitHub Repo | License |
| :---: | :---: |
| [https://github.com/emidiomorgia/astrea-note](https://github.com/emidiomorgia/astrea-note) | [![License][license-badge]][license-link] |

---

## ✨ Abstract: Il Vostro Registro Finanziario di Ordine ed Efficienza

**Astrea Note** è la soluzione software definitiva, **Open Source**, per la **gestione, l'archiviazione e l'invio telematico** delle note spese aziendali.

Ispirato ad **Astrea**, la figura mitologica che incarna l'ordine e la giustizia, il nostro progetto è stato creato per **eliminare il caos** della rendicontazione manuale, garantendo che ogni transazione sia trasformata in un dato **pulito, tracciabile e conforme**.

## 🏛️ Architettura e Sviluppo

Il progetto adotta una **Monorepo** per supportare efficacemente il **Trunk Based Development (TBD)** e garantire *commit* atomici tra tutti i servizi.

### Struttura dei Componenti

L'applicazione è suddivisa in **cinque microservizi backend**, un **Backend For Frontend (BFF)** e un **Frontend**:

| Componente | Descrizione | Linguaggio |
| :--- | :--- | :--- |
| **frontend** | Interfaccia utente web/mobile. | [Es. React/Vue/etc.] |
| **bff** | Strato intermedio ottimizzato per le chiamate UI. | Quarkus (Java 21) |
| **identity-micro** | Gestione di Autenticazione (AuthN) e Autorizzazione (AuthZ). | Quarkus (Java 21) |
| **notes-micro** | Logica principale per la creazione e la gestione delle singole note spese. | Quarkus (Java 21) |
| **reports-micro** | Gestione della logica di aggregazione e generazione dei report contabili. | Quarkus (Java 21) |
| **common-data-micro** | Gestione dei dati comuni statici o di configurazione. | Quarkus (Java 21) |

### Stato dei Componenti (Build & Quality)

Lo stato di integrazione e la qualità del codice per ogni componente sono tracciati di seguito.

| Componente | Build Status | Test Coverage | Sonar Quality |
| :--- | :---: | :---: | :---: |
| `frontend` | [![Build Status][fe-build-badge]][fe-build-link] | [![Test Coverage][fe-coverage-badge]][fe-coverage-link] | [![Quality Gate][fe-quality-badge]][fe-quality-link] |
| `bff` | [![Build Status][bff-build-badge]][bff-build-link] | [![Test Coverage][bff-coverage-badge]][bff-coverage-link] | [![Quality Gate][bff-quality-badge]][bff-quality-link] |
| `identity-micro` | [![Build Status][id-build-badge]][id-build-link] | [![Test Coverage][id-coverage-badge]][id-coverage-link] | [![Quality Gate][id-quality-badge]][id-quality-link] |
| `notes-micro` | [![Build Status][notes-build-badge]][notes-build-link] | [![Test Coverage][notes-coverage-badge]][notes-coverage-link] | [![Quality Gate][notes-quality-badge]][notes-quality-link] |
| `reports-micro` | [![Build Status][reports-build-badge]][reports-build-link] | [![Test Coverage][reports-coverage-badge]][reports-coverage-link] | [![Quality Gate][reports-quality-badge]][reports-quality-link] |
| `common-data-micro` | [![Build Status][cd-build-badge]][cd-build-link] | [![Test Coverage][cd-coverage-badge]][cd-coverage-link] | [![Quality Gate][cd-quality-badge]][cd-quality-link] |

### Core Technologies

* **Backend Runtime:** **Java Quarkus** running on **JDK 21 LTS**.
* **Monorepo Tooling:** [e.g., Nx / Turborepo]
* **Persistence/Messaging (Local Dev):** **MongoDB** and **Kafka**.
* **Deployment Strategy:** **Quarkus Native** compilation via **Dockerfile** for production images, orchestrated da **Kubernetes** (`/deployment` folder).

---

## 🛠️ Come Iniziare (Getting Started)

### Prerequisiti

* **Java Development Kit (JDK) 21 (LTS)**
* **Maven o Gradle**
* **Docker e Docker Compose** (richiesti per eseguire i servizi di runtime locali)
* [Monorepo Tooling CLI, es. `npm install -g nx`]

### Setup Locale

1.  Clona il repository:
    ```bash
    git clone [https://github.com/emidiomorgia/astrea-note.git](https://github.com/emidiomorgia/astrea-note.git)
    cd astrea-note
    ```
2.  Installa le dipendenze:
    ```bash
    npm install
    ```
3.  **Avvia i Servizi di Runtime (Mongo e Kafka):**
    Dalla directory principale, usa Docker Compose:
    ```bash
    docker compose up -d
    ```
4.  **Compila e Avvia i Componenti:**
    Avvia i componenti di interesse (esempio con un microservizio e il frontend):
    ```bash
    # Avvia un microservizio Quarkus in modalità sviluppo
    cd services/notes-micro/
    ./mvnw quarkus:dev
    
    # Avvia il Frontend (dipende dal tool Monorepo)
    nx serve frontend 
    ```

---

## 🤝 Contribuire (Contributing)

Siamo un progetto Open Source e accogliamo con favore tutti i contributi!

A causa del nostro modello **Trunk Based Development** e **Monorepo**, si prega di osservare le seguenti linee guida:

1.  **Issue:** Discuti le modifiche più grandi creando prima un'issue.
2.  **Branch Brevi:** Lavora su *branch* di breve durata e *merge* frequentemente sulla `main`.
3.  **Test e Scope:** Assicurati di testare solo i componenti che hai modificato. Usa i comandi del *Monorepo Tooling* (es. `nx affected:test`) per limitare l'esecuzione dei test.
4.  **Commit Atomici:** Se la tua funzionalità coinvolge più componenti (es. `frontend` e `bff`), includi tutte le modifiche in un unico commit/PR.

Consulta il file [`CONTRIBUTING.md`](CONTRIBUTING.md) per i dettagli completi.

---

## 📄 Licenza

Questo progetto è distribuito sotto licenza **[Es. MIT / Apache 2.0]**. Vedere il file [`LICENSE`](LICENSE) per i dettagli.

---

### Badge Placeholder URLs (Sostituisci i link con quelli reali)

[license-badge]: https://img.shields.io/badge/License-[License%20Name]-blue.svg
[license-link]: LICENSE

[fe-build-badge]: https://img.shields.io/github/actions/workflow/status/emidiomorgia/astrea-note/frontend-ci.yml?branch=main&style=flat-square&label=frontend
[fe-build-link]: https://github.com/emidiomorgia/astrea-note/actions
[fe-coverage-badge]: https://img.shields.io/codecov/c/github/emidiomorgia/astrea-note/main?flag=frontend&style=flat-square&label=coverage
[fe-coverage-link]: https://codecov.io/gh/emidiomorgia/astrea-note
[fe-quality-badge]: https://img.shields.io/sonarcloud/quality/emidiomorgia_astrea-note/frontend?style=flat-square&label=quality
[fe-quality-link]: https://sonarcloud.io/dashboard?id=emidiomorgia_astrea-note

[bff-build-badge]: https://img.shields.io/github/actions/workflow/status/emidiomorgia/astrea-note/bff-ci.yml?branch=main&style=flat-square&label=bff
[bff-build-link]: https://github.com/emidiomorgia/astrea-note/actions
[bff-coverage-badge]: https://img.shields.io/codecov/c/github/emidiomorgia/astrea-note/main?flag=bff&style=flat-square&label=coverage
[bff-coverage-link]: https://codecov.io/gh/emidiomorgia/astrea-note
[bff-quality-badge]: https://img.shields.io/sonarcloud/quality/emidiomorgia_astrea-note/bff?style=flat-square&label=quality
[bff-quality-link]: https://sonarcloud.io/dashboard?id=emidiomorgia_astrea-note

[id-build-badge]: https://img.shields.io/github/actions/workflow/status/emidiomorgia/astrea-note/identity-ci.yml?branch=main&style=flat-square&label=identity
[id-build-link]: https://github.com/emidiomorgia/astrea-note/actions
[id-coverage-badge]: https://img.shields.io/codecov/c/github/emidiomorgia/astrea-note/main?flag=identity&style=flat-square&label=coverage
[id-coverage-link]: https://codecov.io/gh/emidiomorgia/astrea-note
[id-quality-badge]: https://img.shields.io/sonarcloud/quality/emidiomorgia_astrea-note/identity?style=flat-square&label=quality
[id-quality-link]: https://sonarcloud.io/dashboard?id=emidiomorgia_astrea-note

[notes-build-badge]: https://img.shields.io/github/actions/workflow/status/emidiomorgia/astrea-note/notes-ci.yml?branch=main&style=flat-square&label=notes
[notes-build-link]: https://github.com/emidiomorgia/astrea-note/actions
[notes-coverage-badge]: https://img.shields.io/codecov/c/github/emidiomorgia/astrea-note/main?flag=notes&style=flat-square&label=coverage
[notes-coverage-link]: https://codecov.io/gh/emidiomorgia/astrea-note
[notes-quality-badge]: https://img.shields.io/sonarcloud/quality/emidiomorgia_astrea-note/notes?style=flat-square&label=quality
[notes-quality-link]: https://sonarcloud.io/dashboard?id=emidiomorgia_astrea-note

[reports-build-badge]: https://img.shields.io/github/actions/workflow/status/emidiomorgia/astrea-note/reports-ci.yml?branch=main&style=flat-square&label=reports
[reports-build-link]: https://github.com/emidiomorgia/astrea-note/actions
[reports-coverage-badge]: https://img.shields.io/codecov/c/github/emidiomorgia/astrea-note/main?flag=reports&style=flat-square&label=coverage
[reports-coverage-link]: https://codecov.io/gh/emidiomorgia/astrea-note
[reports-quality-badge]: https://img.shields.io/sonarcloud/quality/emidiomorgia_astrea-note/reports?style=flat-square&label=quality
[reports-quality-link]: https://sonarcloud.io/dashboard?id=emidiomorgia_astrea-note

[cd-build-badge]: https://img.shields.io/github/actions/workflow/status/emidiomorgia/astrea-note/commondata-ci.yml?branch=main&style=flat-square&label=commondata
[cd-build-link]: https://github.com/emidiomorgia/astrea-note/actions
[cd-coverage-badge]: https://img.shields.io/codecov/c/github/emidiomorgia/astrea-note/main?flag=commondata&style=flat-square&label=coverage
[cd-coverage-link]: https://codecov.io/gh/emidiomorgia/astrea-note
[cd-quality-badge]: https://img.shields.io/sonarcloud/quality/emidiomorgia_astrea-note/commondata?style=flat-square&label=quality
[cd-quality-link]: https://sonarcloud.io/dashboard?id=emidiomorgia_astrea-note
