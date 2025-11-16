# 🌟 Astrea Note

<div align="center">
  <img src="[Logo Placeholder URL]" alt="Astrea Note Logo: minimalist abstract symbol suggesting financial flow and organizational order, rendered in white on a Gemini-blue background." width="200"/>
  <h1>Astrea Note</h1>
  <p>Open Source Expense Report Management Software</p>
</div>

| GitHub Repo | License |
| :---: | :---: |
| [https://github.com/emidiomorgia/astrea-note](https://github.com/emidiomorgia/astrea-note) | [![License][license-badge]][license-link] |

---

## ✨ Abstract: Your Financial Register of Order and Efficiency

**Astrea Note** is the definitive, **Open Source** software solution for the **management, archiving, and electronic submission** of corporate expense reports.

Inspired by **Astrea**, the mythological figure embodying order and justice, our project is designed to **eliminate the chaos** of manual reporting processes. It ensures that every transaction is transformed into **clean, traceable, and compliant financial data.**

---

## 🏛️ Architecture and Development

The project adopts a **Monorepo** structure to effectively support **Trunk Based Development (TBD)** and ensure atomic commits across all interdependent services.

### Component Structure

The application is logically segmented into a Frontend, a BFF, and four core Microservices:

| Component | Description | Technology Stack |
| :--- | :--- | :--- |
| **frontend** | Web/mobile user interface. | [e.g., React/Vue/Next.js] |
| **bff** | Optimized Backend For Frontend layer. | Quarkus (Java 21) |
| **identity-micro** | Handles Authentication (AuthN) and Authorization (AuthZ). | Quarkus (Java 21) |
| **notes-micro** | Core logic for creating and managing individual expense notes. | Quarkus (Java 21) |
| **reports-micro** | Manages aggregation logic and financial report generation. | Quarkus (Java 21) |
| **common-data-micro** | Manages static configuration and global common data. | Quarkus (Java 21) |

### Component Status (Build & Quality)

The continuous integration status and code quality for each component are tracked below.

| Component | Build Status | Test Coverage | Sonar Quality |
| :--- | :---: | :---: | :---: |
| `frontend` | [![Build Status][fe-build-badge]][fe-build-link] | [![Test Coverage][fe-coverage-badge]][fe-coverage-link] | [![Quality Gate][fe-quality-badge]][fe-quality-link] |
| `bff` | [![Build Status][bff-build-badge]][bff-build-link] | [![Test Coverage][bff-coverage-badge]][bff-coverage-link] | [![Quality Gate][bff-quality-badge]][bff-quality-link] |
| `identity-micro` | [![Build Status][id-build-badge]][id-build-link] | [![Test Coverage][id-coverage-badge]][id-coverage-link] | [![Quality Gate][id-quality-badge]][id-quality-link] |
| `notes-micro` | [![Build Status][notes-build-badge]][notes-build-link] | [![Test Coverage][notes-coverage-badge]][notes-coverage-link] | [![Quality Gate][notes-quality-badge]][notes-quality-link] |
| `reports-micro` | [![Build Status][reports-build-badge]][reports-build-link] | [![Test Coverage][reports-coverage-badge]][reports-coverage-link] | [![Quality Gate][reports-quality-badge]][reports-quality-link] |
| `common-data-micro` | [![Build Status][cd-build-badge]][cd-build-link] | [![Test Coverage][cd-coverage-badge]][cd-coverage-link] | [![Quality Gate][cd-quality-badge]][cd-quality-link] |

### Core Technologies

* **Backend Runtime:** **Java Quarkus** running on **JDK 21 LTS** (Leveraging Virtual Threads for high performance).
* **Monorepo Tooling:** [e.g., Nx / Turborepo]
* **Persistence/Messaging (Local Dev):** **MongoDB** and **Kafka**.
* **Deployment Strategy:** **Quarkus Native** compilation via **Dockerfile**, orchestrated by **Kubernetes** (files located in the `/deployment` folder).

---

## 🛠️ Getting Started

### Prerequisites

* **Java Development Kit (JDK) 21 (LTS)**
* **Maven or Gradle**
* **Docker and Docker Compose** (required to run local runtime services)
* [Monorepo Tooling CLI, e.g., `npm install -g nx`]

### Local Setup

1.  Clone the repository:
    ```bash
    git clone [https://github.com/emidiomorgia/astrea-note.git](https://github.com/emidiomorgia/astrea-note.git)
    cd astrea-note
    ```
2.  Install dependencies:
    ```bash
    npm install
    ```
3.  **Start Runtime Services (Mongo and Kafka):**
    From the root directory, use Docker Compose:
    ```bash
    docker compose up -d
    ```
4.  **Build and Run Components:**
    Start the components of interest (example launching a microservice and the frontend):
    ```bash
    # Start a Quarkus microservice in development mode
    cd services/notes-micro/
    ./mvnw quarkus:dev
    
    # Start the Frontend (using Monorepo Tooling)
    nx serve frontend 
    ```

### Production Deployment

Microservices are built using **Quarkus Native** (via GraalVM) for optimal performance. The required build steps are contained within the dedicated **Dockerfile** in each service folder. Deployment to production is handled via the YAML files located in the **/deployment** directory.

---

## 🤝 Contributing

As an Open Source project, we welcome all contributions!

Due to our **Trunk Based Development** and **Monorepo** structure, please observe the following guidelines:

1.  **Issues:** Discuss major changes by opening an issue first.
2.  **Short-Lived Branches:** Work on short-lived branches and merge frequently into `main`.
3.  **Testing and Scope:** Ensure you only test the components you have modified. Use Monorepo Tooling commands (e.g., `nx affected:test`) to limit test execution scope.
4.  **Atomic Commits:** If your feature affects multiple components (e.g., `frontend` and `bff`), include all changes in a single, cohesive commit/PR.

Please review the [`CONTRIBUTING.md`](CONTRIBUTING.md) file for full details.

---

## 📄 License

This project is licensed under the **[e.g., MIT / Apache 2.0]** License. See the [`LICENSE`](LICENSE) file for details.

---

### Badge Placeholder URLs (Using the provided GitHub repository)

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
