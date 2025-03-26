# MCP Server Setup

## 🚀 Schnellstart

1. Erstelle eine `config.json` im Projektordner
2. Füge die benötigten Server hinzu
3. Starte mit den Basis-Funktionen
4. Erweitere nach Bedarf

## 📝 Basis-Konfiguration

```json
{
  "servers": {
    "filesystem": {
      "command": "npx",
      "args": ["@anthropic-ai/mcp-server-filesystem"]
    },
    "shell-commander": {
      "command": "npx",
      "args": ["@anthropic-ai/mcp-server-shell-commander"]
    }
  }
}
```

## 💡 Verfügbare Server

### Filesystem
- Dateizugriff
- Ordner durchsuchen
- Dateien bearbeiten

### Shell Commander
- Befehle ausführen
- Programme starten
- Systeminformationen abrufen

### Puppeteer
- Webseiten automatisieren
- Screenshots erstellen
- Formulare ausfüllen

### Brave Search
- Websuche durchführen
- Lokale Suche nutzen
- Aktuelle Informationen finden

### SQLite
- Datenbank erstellen
- Daten speichern
- Abfragen ausführen

### GitHub
- Repositories verwalten
- Code hochladen
- Issues bearbeiten

## 🔧 Erweiterte Konfiguration

### Puppeteer für Web-Automation
```json
{
  "servers": {
    "puppeteer": {
      "command": "npx",
      "args": ["@anthropic-ai/mcp-server-puppeteer"]
    }
  }
}
```

### Brave Search für Recherche
```json
{
  "servers": {
    "brave-search": {
      "command": "npx",
      "args": ["@anthropic-ai/mcp-server-brave-search"],
      "env": {
        "BRAVE_API_KEY": "dein-api-key"
      }
    }
  }
}
```

### SQLite für Datenbank
```json
{
  "servers": {
    "sqlite": {
      "command": "npx",
      "args": ["@anthropic-ai/mcp-server-sqlite"]
    }
  }
}
```

### GitHub für Versionskontrolle
```json
{
  "servers": {
    "github": {
      "command": "npx",
      "args": ["@anthropic-ai/mcp-server-github"],
      "env": {
        "GITHUB_TOKEN": "dein-github-token"
      }
    }
  }
}
```

## ⚠️ Häufige Probleme

### Server startet nicht
1. Prüfe die Konfiguration
2. Kontrolliere die Pfade
3. Überprüfe die Berechtigungen

### API Keys funktionieren nicht
1. Prüfe die Umgebungsvariablen
2. Kontrolliere die Gültigkeit
3. Erneuere wenn nötig

### Dateizugriff fehlgeschlagen
1. Prüfe die Pfade
2. Kontrolliere die Berechtigungen
3. Überprüfe den Dateistatus

## 💪 Tipps für den Erfolg

1. **Start klein**
   - Beginne mit Filesystem
   - Füge Server nach Bedarf hinzu
   - Teste schrittweise

2. **Sicherheit beachten**
   - API Keys sicher speichern
   - Berechtigungen prüfen
   - Zugriffe kontrollieren

3. **Hilfe finden**
   - Dokumentation lesen
   - Community fragen
   - Support kontaktieren
