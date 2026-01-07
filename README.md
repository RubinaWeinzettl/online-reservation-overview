# Online Reservierung – Projekt Overview

Dieses Repository dient als **zentrale Übersicht** für mein Portfolio-Projekt **Online Reservierung**.  
Es beschreibt Zielsetzung, Architektur, Vorgehensweise und den aktuellen Entwicklungsstand und verlinkt die zugehörigen Code-Repositories.

Das Projekt befindet sich bewusst im **Work-in-Progress-Status** und wird inkrementell weiterentwickelt.

---

## Überblick

Die Online-Reservierung ist eine **serviceorientierte Webanwendung** für zwei unterschiedliche Nutzergruppen:

- **Kund:innen**, die Termine buchen möchten  
- **Unternehmen** (z. B. Friseur-, Massage- oder Nagelstudios), die Leistungen, Personal und Buchungen verwalten  

Der Schwerpunkt dieses Projekts liegt nicht nur auf Funktionalität, sondern vor allem auf:

- Architekturentscheidungen  
- klarer Trennung von Verantwortlichkeiten  
- realistischen Entwicklungs- und Release-Zyklen  
- Qualitätssicherung und Deployment-Strategien  

---

## Architektur – aktueller Stand

Die Anwendung ist modular aufgebaut und besteht aus folgenden Kernkomponenten:

### Auth Service
Eigenständiger Backend-Service für:
- Anmeldung und Authentifizierung  
- JWT-basierte Token  
- Rollenmodell (**Role Based Access Control – RBAC**)

### Zentrales Backend (FastAPI)
Gemeinsame API für Business- und Customer-Funktionalitäten, intern klar modularisiert, z. B.:

- Business-Module  
- Customer-Module  
- Booking-Module  

inklusive:
- **RBAC**
- **Tenant Checks** (Zugriff nur im Kontext des zugehörigen Unternehmens)

### Frontend (schrittweise umgesetzt)
- **Release 1:** sehr einfache HTML-Oberfläche zur Validierung der API-Flows  
- **Spätere Releases:** Migration auf **React** mit rollenbasierter Navigation

### Datenbank
- **MariaDB**
- containerisiert für lokale Entwicklung

Die Architektur ist so gewählt, dass **frühe Releases möglich sind**, während spätere Erweiterungen (z. B. UI-Framework, feinere Service-Trennung) konzeptionell vorbereitet bleiben.

---

## Mandantenfähigkeit

Die Mandantenfähigkeit wird **mehrschichtig** umgesetzt:

- **Anwendungsebene:**  
  - Role Based Access Control (RBAC)  
  - Tenant Checks (z. B. `business_id` / `tenant_id`)

- **Plattformebene (Zielumgebung):**  
  - Kubernetes-Deployment mit **Namespaces pro Mandant**  
  - Trennung von Konfigurationen, Ressourcen und Deployments

---

## Entwicklungs- & Zielumgebung

### Lokale Entwicklung
- Docker-basierte Container  
- Orchestrierung über **ddev**  
- reproduzierbare Entwicklungsumgebung  
- realistisches Service-Setup bereits im lokalen Betrieb

### Zielumgebung
- Deployment auf einen **Kubernetes-Cluster**
- Vorbereitung der Docker-Images und Konfigurationen von Beginn an
- Kubernetes wird **nicht** für frühe Releases erzwungen, ist aber klar als Zielplattform vorgesehen

---

## Release-Strategie

Das Projekt wird **inkrementell** entwickelt.  
Der vollständige Funktionsumfang entsteht über mehrere Releases.

### Release 1 – MVP (bewusst reduziert)

**Auth**
- Anmeldung mit Benutzername / Passwort  
- keine Kund:innen-Registrierung  
- Fokus auf technische Basis (JWT, Rollen, Zugriff)

**Backend / API**
- Anlegen eines Unternehmens  
- Pflege eines einfachen Dienstplans (freie / belegte Zeitfenster)  
- Anlegen von Kund:innen durch Unternehmen  
- Terminbuchung in freien Zeitslots  
- keine komplexen Business-Regeln

**Frontend**
- sehr einfache HTML-Oberfläche
- Fokus auf Funktionalität statt UI-Design

Ziel dieses Releases ist ein **stabiler End-to-End-Flow**, kein vollständiges Produkt.

### Weitere geplante Releases (Ausblick)

- Migration des Frontends auf **React**
- Kund:innen-Registrierung
- Login via **OAuth** (externe Identity Provider)
- Erweiterung von Buchungs- und Rollenmodellen
- Ausbau von Tests, Validierungen und Business-Logik
- CI/CD-Vertiefung
- Kubernetes-Deployment

---

## CI/CD & Qualitätssicherung

Geplant bzw. schrittweise umgesetzt:

- Docker-basierte Containerisierung aller Komponenten  
- **GitHub Actions** für:
  - Linting (Backend & Frontend)
  - automatisierte Tests
  - Build der Container Images
- klare Trennung von:
  - Code-Qualität
  - Tests
  - Build-Schritten

Die Pipeline ist so ausgelegt, dass sie sowohl lokale Entwicklung als auch spätere Kubernetes-Deployments unterstützt.

---

## Zielbild

In der finalen Ausbaustufe soll die Anwendung:

- zwei klar getrennte Nutzererlebnisse (Business / Kund:innen) bieten  
- eine saubere, erweiterbare Backend-Architektur besitzen  
- moderne Authentifizierungs- und Autorisierungsmechanismen nutzen  
- containerisiert und orchestriert auf Kubernetes laufen  
- reale Entwicklungs-, Release- und Betriebsprozesse abbilden  

---

## Repositories

- **Projekt-Overview:**  
  https://github.com/RubinaWeinzettl/online-reservation-overview

- **Auth Service:**  
  https://github.com/RubinaWeinzettl/online-reservation-auth

- **API:**  
  https://github.com/RubinaWeinzettl/online-reservation-api

- **Web:**  
  https://github.com/RubinaWeinzettl/online-reservation-web
