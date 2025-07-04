# 📌 Projet : Speed Meeting (Teams)

## 🧰 Technologies principales

| Technologie                             | Rôle dans le projet                                          |
| --------------------------------------- | ------------------------------------------------------------ |
| **Angular**                             | Frontend (formulaire d’inscription, interface utilisateur)   |
| **Spring Boot**                         | Backend Java (API REST, logique métier)                      |
| **Base de données SQL (H2/PostgreSQL)** | Stockage des inscriptions                                    |
| **Microsoft Graph API**                 | Intégration avec Microsoft Teams (envoi de message, réunion) |
| **OAuth2 (Azure AD)**                   | Authentification sécurisée pour accéder à Graph API          |
| **Git**                                 | Gestion de version                                           |
| **Obsidian**                            | Documentation et suivi du projet                             |

---

### 📋 **Plan de Développement**

### 1. **Backend (Spring Boot)**

- [x] Configuration initiale : Java + Spring Boot via Spring Initializr
- [x] Modélisation : Classe `User` avec validations (nom, prénom, email)
- [x] **Persistence avec Spring Data JPA** :
    - Interfaces `Repository` basées sur `JpaRepository`
    - Méthodes CRUD standards (save, findById, findAll, delete)
    - Service métier avec logique applicative
- [x] API REST  :
    - Endpoints
    - Gestion élégante des exceptions

---

### 2. **Base de données**

- [x] Environnement dev : H2 avec console de debug
- [ ] Préparation prod : Migration PostgreSQL (Flyway)
- [x] Architecture JPA : Entités et relations via Spring Data
- [x] Sécurité transactionnelle (`@Transactional`)

---

### 3. **Frontend Angular**

- [x] Setup technique : Angular + Node.js LTS
- [x] Interface inscription : Formulaire validé
- [x] Communication backend :
    - Gestion élégante des erreurs avec feedback utilisateur
- [x] UX : Système de notifications moderne
- [x] Expérience fluide : Indicateurs de chargement

---

### 4. **Tests d'intégration**

- [ ] Validation end-to-end : inscription → stockage → confirmation
- [ ] Tests automatisés : Postman + JUnit
- [ ] Débogage communication front-back
- [ ] Optimisation performances globales

---

### 5. **Sécurité Azure AD**

- [ ] Configuration Azure AD :
    - Architecture application adaptée
    - Permissions Graph (Calendars.ReadWrite, OnlineMeetings.ReadWrite)
- [ ] Implémentation OAuth2 :
    - Flux `authorization_code`
    - Gestion `access_token` et `refresh_token`
    - Stockage sécurisé
- [ ] **Gestion avancée des tokens** :
    - Renouvellement automatique (validité 1h)
    - Rotation refresh tokens (usage unique)
    - Mise à jour sécurisée
    - Traitement erreurs (`invalid_grant`)
    - Monitoring expirations (14j inactivité, 90j max)
- [ ] Service backend : Renouvellement intelligent des tokens

---

### 6. **Teams Integration**

- [ ] Réunions Teams via Graph API :
    - Format JSON optimisé + emails participants
    - Gestion fuseaux horaires (ISO8601)
- [ ] Algorithme matchmaking pour réunions
- [ ] Système notifications Teams
- [ ] Gestion résiliente des erreurs API
- [ ] Fiabilité : Reconnexion automatique

---

### 7. **Finalisation**

- [ ] Test complet du workflow
- [ ] Évaluation performance sous charge
- [ ] Polissage UX et optimisations
- [ ] Documentation technique exhaustive