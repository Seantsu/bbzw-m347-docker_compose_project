# Architektur des TicketBoard-Systems

## Übersicht

Das TicketBoard-System besteht aus vier Services, die in Docker Containern laufen:

- **Frontend**: Nginx-Server, der eine statische HTML-Seite serviert (Port 3000)
- **API**: FastAPI-Anwendung, die die Geschäftslogik bereitstellt (Port 8000)
- **DB**: PostgreSQL-Datenbank für Datenpersistenz
- **Adminer**: Web-Interface zur Datenbankverwaltung (Port 8080)

## Kommunikation

- Frontend kommuniziert mit API über HTTP
- API kommuniziert mit DB über PostgreSQL-Protokoll
- Alle Services laufen im gleichen Docker-Network und finden sich über Servicenamen

## Persistenz

- Datenbankdaten werden in einem benannten Volume gespeichert
- Volume überlebt Container-Neustarts und -Löschungen

## Konfiguration

- Umgebungsvariablen in .env-Datei
- Compose-Datei definiert alle Services und deren Abhängigkeiten