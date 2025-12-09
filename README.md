# online-reservation-overview
Overview meines Lernprojekts: Eine Online-Reservierungsplattform als Einstieg in Microservices, FastAPI und moderne Webarchitektur.

📘 Online Reservierung – Projekt Overview

Ein Microservice-Lernprojekt mit FastAPI & React

🌿 Über dieses Projekt

Dieses Repository dient als zentrale Übersicht über mein Portfolio-Projekt Online Reservierung.
Es fasst Architektur, Ziele, Systemaufbau und die zugehörigen Code-Repositories zusammen.

Das Projekt ist mein persönlicher Lernraum, um Microservice-Architekturen zum ersten Mal selbst umzusetzen und meine bisherigen Erfahrungen im Web Application Development bewusst zu erweitern – mit Fokus auf:

Microservices

Python / FastAPI

React

Backend-for-Frontend (BFF) Pattern

Rollenbasierter Authentifizierung

DevOps-Grundlagen

🎯 Projektziel

Das Ziel ist es, eine Online-Reservierungsplattform zu entwickeln, auf der:

Kund*innen Termine buchen können

Unternehmen wie Friseur-, Massage- oder Nagelstudios

Leistungen anlegen

Personal verwalten

Buchungen organisieren

Gleichzeitig lerne ich an diesem Projekt die Grundlagen einer modernen, serviceorientierten Architektur kennen.

🧱 Systemarchitektur

Das System besteht aus mehreren voneinander getrennten Repositories.
Jedes Repository bildet eine klar abgegrenzte Komponente:

1. Auth-Service

Zuständig für:

Registrierung

Login

JWT-basierte Authentifizierung

Rollen & Weiterleitung ins richtige Frontend

🔗 Repository:
https://github.com/RubinaWeinzettl/online-reservation-auth

2. Business-App (Frontend + Business-BFF)

Für Unternehmen & Mitarbeiter*innen:

Personalverwaltung

Leistungen & Dauer

Dienstpläne

Verwaltung von Buchungsanfragen

Terminübersichten

🔗 Repository:
<Link zu Business-App Repo - TBA>

3. Customer-App (Frontend + Customer-BFF)

Für Kund*innen:

Registrierung / Login

Kalenderansicht

Auswahl der Fachkraft

Terminbuchung

Stornierung / Übersicht

🔗 Repository:
<Link zu Customer-App - TBA>

🗂 Architekturdiagramm
graph LR
  subgraph Clients
    CBrowser[Customer Browser]
    BBrowser[Business Browser]
  end

  subgraph Frontends
    CFE[Customer Frontend (React)]
    BFE[Business Frontend (React)]
  end

  subgraph BFF_Layer[Backend for Frontend]
    CBFF[Customer BFF (FastAPI)]
    BBFF[Business BFF (FastAPI)]
  end

  subgraph Services
    AUTH[Auth Service]
    BOOK[Booking Service<br/>(Basic Version)]
    BUS[Business Service<br/>(Unternehmen + Staff)]
  end

  subgraph Databases
    DBAUTH[(Auth DB)]
    DBBOOK[(Booking DB)]
    DBBUS[(Business DB)]
  end

  %% Connections
  CBrowser --> CFE
  BBrowser --> BFE

  CFE --> CBFF
  BFE --> BBFF

  CBFF --> AUTH
  BBFF --> AUTH

  CBFF --> BOOK
  BBFF --> BOOK

  CBFF --> BUS
  BBFF --> BUS

  AUTH --> DBAUTH
  BOOK --> DBBOOK
  BUS --> DBBUS

  AUTH -. JWT Tokens .-> CFE
  AUTH -. JWT Tokens .-> BFE

🛠 Technologien
Backend

Python

FastAPI

JWT Authentication

PostgreSQL / SQLite

Docker

Frontend

React

TypeScript

React Router

Zustand oder Redux Toolkit

TailwindCSS (optional)

Tools / DevOps

GitHub Projects (Organisation)

GitHub Actions (optional CI/CD)

Docker Compose

📚 Was ich mit diesem Projekt lerne

Aufbau und Strukturierung von Microservices

Trennung von Verantwortlichkeiten

API-Design für unterschiedliche Userrollen

Umsetzung eines eigenen Auth-Services

Arbeiten mit JWT & Rollenmodellen

Anwendung des Backend-for-Frontend Patterns

Domänenorientiertes Denken

Entscheidungsfindung in der Architektur

Dieses Projekt wächst Schritt für Schritt und begleitet mich in meiner Weiterentwicklung als Web Application Developerin mit DevOps-Fokus.

🚀 Status

Dieses Projekt befindet sich im aktiven Aufbau.
Neue Funktionen und Services werden laufend ergänzt.

🤝 Feedback & Austausch

Ich freue mich über Rückmeldungen oder Impulse – besonders zu Architektur, Codequalität oder Erweiterungsmöglichkeiten.
