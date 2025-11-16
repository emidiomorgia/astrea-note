# 🌟 Astrea Note



| CI/CD Status | Test Coverage | SonarQube Quality |
| :---: | :---: | :---: |
| [![Build Status][build-badge]][build-link] | [![Test Coverage][coverage-badge]][coverage-link] | [![Quality Gate][quality-badge]][quality-link] |

---

## ✨ Abstract: Your Financial Register of Order and Efficiency

**Astrea Note** is the definitive, **Open Source** software solution for the **management, archiving, and electronic submission** of corporate expense reports.

Inspired by **Astrea**, the mythological figure embodying order and justice, our project is designed to **eliminate the chaos** of manual reporting processes. It ensures that every transaction is transformed into **clean, traceable, and compliant financial data.**

---

## 🚀 Key Features & Vision

Our primary goal is to provide a system that supports the principle of **financial correctness** (Astrea's Justice) through **maximum operational efficiency**.

* **Rapid Reporting:** Intuitive user interface for quick receipt capture and submission.
* **Orderly Workflow:** Configurable approval flows and real-time tracking of reimbursement status.
* **Compliance:** Secure document storage and standardized accounting export support.
* **Trunk Based Development (TBD):** We prioritize stability with continuous integration onto the `main` branch.

## 🏛️ Architecture and Development

This project uses a **Monorepo** structure, which is critical for enforcing the **Trunk Based Development** model by enabling atomic commits across services. This structure ensures maximum cohesion and rapid integration between components.

The codebase is logically organized into the following directories:

* `/frontend`: Web and/or mobile application (e.g., React/Vue).
* `/bff`: Backend For Frontend, optimized for specific client needs.
* `/services`: Independent Microservices (built with Quarkus).
* `/shared`: Common libraries, API contracts, and Design System components.
* **/deployment**: Contains all necessary **Kubernetes YAML files** for deployment.

### Core Technologies

* **Backend Runtime:** **Java Quarkus** running on **JDK 21 LTS** (ensuring high performance and low memory footprint).
* **Monorepo Tooling:** [e.g., Nx / Turborepo]
* **Persistence/Messaging (Local Dev):** **MongoDB** and **Kafka**.
* **Deployment Strategy:** **Quarkus Native** compilation via **Dockerfile** for production images, orchestrated by **Kubernetes**.

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
2.  Installa le dipendenze:
    ```bash
    npm install
    ```
3.  **Start Runtime Services (Mongo and Kafka):**
    From the root directory, use Docker Compose:
    ```bash
    docker compose up -d
    ```
4.  **Build and Run the Frontend/BFF:**
    Start the components of interest (example using an assumed service name):
    ```bash
    # Build and run a Quarkus microservice in development mode
    cd services/expense-service/
    ./mvnw quarkus:dev
    
    # Or start the Frontend
    nx serve frontend 
    ```

### Production Deployment

Microservices are built using **Quarkus Native** (via GraalVM) for optimal performance. The required build steps are contained within the dedicated **Dockerfile** in each service folder.

Deployment to production is handled via the YAML files located in the **/deployment** directory.

---

## 🤝 Contributing

As an Open Source project, we welcome all contributions!

Due to our **Trunk Based Development** and **Monorepo** structure, please observe the following guidelines:

1.  **Issues:** Discuss large changes by opening an issue first.
2.  **Short-Lived Branches:** Work on short-lived branches and merge frequently into `main`.
3.  **Atomic Commits:** If your feature affects multiple components (e.g., `frontend` and a `service`), ensure all changes are included in a single, cohesive commit/PR.
4.  **Testing:** Use monorepo commands (e.g., `nx affected:test`) to run tests only for the services you modified.

Please review the [`CONTRIBUTING.md`](CONTRIBUTING.md) file for full details.

---

## 📄 License

This project is licensed under the **[e.g., MIT / Apache 2.0]** License. See the [`LICENSE`](LICENSE) file for details.

---

### Badge Placeholder URLs (Using your GitHub repository)

[build-badge]: https://img.shields.io/github/actions/workflow/status/emidiomorgia/astrea-note/ci.yml?branch=main&style=flat-square
[build-link]: https://github.com/emidiomorgia/astrea-note/actions
[coverage-badge]: https://img.shields.io/codecov/c/github/emidiomorgia/astrea-note/main?style=flat-square
[coverage-link]: https://codecov.io/gh/emidiomorgia/astrea-note
[quality-badge]: https://img.shields.io/sonarcloud/quality/emidiomorgia_astrea-note?style=flat-square
[quality-link]: https://sonarcloud.io/dashboard?id=emidiomorgia_astrea-note
