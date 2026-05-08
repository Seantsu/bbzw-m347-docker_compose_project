# Fragen – Integration der Services (DL10)

Name: Hofstetter Travis
Klasse: M347

---

## 1. Services verstehen

Welche Services haben Sie in Ihrer `compose.yaml` definiert?

Antwort: api, db, adminer, frontend

---

Welche Aufgabe hat jeder Service in Ihrem System?

Antwort:
- api: Stellt die REST-API bereit (FastAPI)
- db: Speichert Daten persistent (PostgreSQL)
- adminer: Ermöglicht Web-Zugriff auf die Datenbank
- frontend: Serviert die Benutzeroberfläche (Nginx)

---

## 2. Service-Kommunikation

Welchen Servicenamen verwendet die API, um die Datenbank zu erreichen?

Antwort: db

---

Warum funktioniert `localhost` innerhalb eines Containers nicht für die Kommunikation mit anderen Services?

Antwort: localhost bezieht sich auf den eigenen Container, nicht auf andere Services im Netzwerk.

---

Wie stellt Docker Compose sicher, dass sich Services gegenseitig finden können?

Antwort: Durch ein automatisch erstelltes Docker-Netzwerk, in dem Services über ihre Namen erreichbar sind.

---

## 3. Ports und Zugriff

Über welche Ports sind folgende Services erreichbar?

* API: 8000
* Adminer: 8080
* Frontend: 3000

Antwort:

---

Welcher Unterschied besteht zwischen:

* Container-Port: Port innerhalb des Containers
* Host-Port: Port auf dem Host-System, über den der Container-Port exposed wird

Antwort:

---

## 4. Persistenz

Was passiert mit den Daten, wenn ein Container ohne Volume gelöscht wird?

Antwort: Die Daten gehen verloren, da sie nur im Container-Dateisystem gespeichert waren.

---

Wie haben Sie die Persistenz für die Datenbank umgesetzt?

Antwort: Durch Definition eines named Volumes "postgres_data" für den DB-Service.

---

Warum ist ein Volume für die Datenbank notwendig?

Antwort: Um Daten über Container-Neustarts und -Löschungen hinaus zu erhalten.

---

## 5. Compose-Konfiguration

Welche Elemente haben Sie in Ihrer `compose.yaml` definiert?

Antwort: services (api, db, adminer, frontend), volumes (postgres_data)

---

Welche Umgebungsvariablen sind für die Datenbank-Verbindung notwendig?

Antwort: POSTGRES_DB, POSTGRES_USER, POSTGRES_PASSWORD, POSTGRES_HOST, POSTGRES_PORT

---

Wofür wird `depends_on` verwendet?

Antwort: Um die Startreihenfolge der Services zu steuern (API startet nach DB)

---

## 6. Systemtest

Hat das System beim ersten Start vollständig funktioniert?

Antwort:

---

Welche Probleme sind aufgetreten?

Antwort:

---

Wie haben Sie diese Probleme gelöst?

Antwort:

---

## 7. Verständnis

Beschreiben Sie kurz den Datenfluss in Ihrem System.

(Beispiel: Frontend → API → Datenbank)

Antwort:

---

Was passiert beim Befehl:

```bash
docker compose down
```

Antwort:

---

## 8. Reflexion

Was war für Sie heute die wichtigste Erkenntnis?

Antwort:

---

Was war schwierig oder noch unklar?

Antwort:
