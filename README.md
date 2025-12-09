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
<Link zu Customer-App Repo - TBA >
