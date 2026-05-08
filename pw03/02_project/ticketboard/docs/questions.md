# Fragen – Konfiguration und Umgebungsvariablen (DL11)

Name: Hofstetter Travis
Klasse: M347

---

## 1. Konfiguration

Welche Werte waren ursprünglich hardcoded in `compose.yml` und `app/main.py`?

Antwort: In compose.yml: DATABASE_URL und POSTGRES_DB, POSTGRES_USER, POSTGRES_PASSWORD. In app/main.py: DATABASE_URL

---

Warum ist es ein Problem, Passwörter direkt in `compose.yml` einzutragen?

Antwort: Sie sind sichtbar im Git-Repository und können von anderen eingesehen werden.

---

Was ist der Unterschied zwischen `.env` und `.env.example`?

Antwort: .env enthält die echten Werte, .env.example ist ein Template ohne sensible Daten.

---

Warum muss `.env` in `.gitignore` eingetragen sein?

Antwort: Damit die Datei nicht ins Git-Repository gelangt und sensible Daten geschützt sind.

---

## 2. Variablen in Compose

Wie referenziert man eine Variable aus `.env` in `compose.yml`?

Antwort: Mit ${VARIABLE_NAME}

---

Was passiert, wenn eine Variable in `.env` fehlt, aber in `compose.yml` verwendet wird?

Antwort: Docker Compose gibt einen Fehler aus.

---

Was zeigt der Befehl `docker compose config`? Wann ist er nützlich?

Antwort: Er zeigt die aufgelöste Konfiguration. Nützlich zum Debuggen von Variablen.

---

## 3. Dockerfile und Build

Warum wird `requirements.txt` in einem eigenen `COPY`-Schritt vor dem App-Code kopiert?

Antwort: Um den Cache besser zu nutzen – requirements ändern sich seltener als Code.

---

Was bewirkt `.dockerignore`? Welche Dateien sollten darin stehen?

Antwort: Es schließt Dateien vom Build-Kontext aus. .env, .git, __pycache__, .venv

---

## 4. Systemtest

Funktioniert `/db-check` nach Ihrer Konfigurationsanpassung?

Antwort: Ja

---

Was zeigt der Endpunkt `/db-check` an, wenn die Verbindung funktioniert?

Antwort: {"db": "connected"}

---

## 5. Reflexion

Was war der wichtigste Schritt in dieser Woche?

Antwort: Auslagerung der Konfiguration in .env und Verwendung von Umgebungsvariablen.

---

Was ist noch unklar oder möchten Sie besser verstehen?

Antwort: Sicherheitsaspekte bei der Verwaltung von Secrets in Produktion.
