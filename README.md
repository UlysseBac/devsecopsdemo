# DevSecOps: UlysseBAC

Ce projet est une démonstration complète d’une chaîne CI/CD sécurisée autour d’une application Spring Boot. Il est conçu dans le cadre d’un projet DevSecOps EFREI.

---

## Stack utilisée

- Spring Boot 3 + Java 17
- Maven 3.8
- Docker (multi-stage build)
- GitHub Actions
- Trivy (scan de vulnérabilités)
- DockerHub
- Ubuntu 22.04

---

## CI/CD – GitHub Actions

Voici les étapes de la chaîne CI/CD :

| Étape              | Outil            | Description |
|--------------------|------------------|-------------|
| Build Java         | Maven            | Compilation du projet avec `mvn clean package` |
| Tests unitaires    | Maven / JUnit    | Lancement automatique via GitHub Actions |
| Build Docker image | Dockerfile       | Image multi-stage optimisée |
| Scan sécurité      | Trivy            | Scan de vulnérabilités sur l'image |
| Push DockerHub     | Docker CLI       | Pousser l'image `ulyssebac/devsecopsdemo:latest` |
| Déploiement        | Docker run       | Déploiement de l'image sur une VM Ubuntu |

---

##  Lancer le projet localement

```bash
docker run -d -p 8080:8080 ulyssebac/devsecopsdemo:latest
```
## Structure du repo
.
├── Dockerfile              # Build de l'image multi-stage
├── pom.xml                 # Projet Maven
├── src/                    # Code source Java
├── .github/workflows/      # Pipeline GitHub Actions
└── README.md               # Documentation du projet

Ulysse BAC – Étudiant EFREI M1


