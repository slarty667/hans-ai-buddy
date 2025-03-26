# MCP-Server Setup und Konfiguration

## Konfigurationsdatei

Die MCP-Server werden in der `config.json` konfiguriert, die sich im Einstellungsbereich der Claude Desktop-App befindet. Die Grundstruktur der Datei sieht so aus:

```json
{
  "mcpServers": {
    "server-name": {
      "command": "command-to-run",
      "args": ["arg1", "arg2"],
      "env": {
        "ENV_VAR": "value"
      }
    }
  }
}
```

## Verfügbare Server

### Filesystem
- **Funktion**: Zugriff auf lokale Dateien und Verzeichnisse
- **Typische Anwendungen**: Dateioperationen, Projektmanagement
- **Konfiguration**:
  ```json
  "filesystem": {
    "command": "npx",
    "args": [
      "-y",
      "@modelcontextprotocol/server-filesystem"
    ]
  }
  ```

### Puppeteer
- **Funktion**: Webautomatisierung und Screenshots
- **Typische Anwendungen**: UI-Tests, Web-Scraping
- **Konfiguration**:
  ```json
  "Puppeteer": {
    "command": "npx",
    "args": [
      "-y",
      "@modelcontextprotocol/server-puppeteer"
    ]
  }
  ```

### Brave Search
- **Funktion**: Web-Suche und Recherche
- **Typische Anwendungen**: Informationsbeschaffung
- **Konfiguration**:
  ```json
  "Brave Search": {
    "command": "env",
    "args": [
      "BRAVE_API_KEY=your-api-key",
      "npx",
      "-y",
      "@modelcontextprotocol/server-brave-search"
    ]
  }
  ```

### SQLite
- **Funktion**: Datenbankoperationen
- **Typische Anwendungen**: Datenmanagement
- **Konfiguration**:
  ```json
  "SQLite": {
    "command": "npx",
    "args": [
      "-y",
      "mcp-server-sqlite-npx",
      "path/to/your/database.db"
    ]
  }
  ```

### MCP Installer
- **Funktion**: Installation und Update von MCP-Servern
- **Typische Anwendungen**: Server-Management
- **Konfiguration**:
  ```json
  "MCP Installer": {
    "command": "npx",
    "args": [
      "-y",
      "@anaisbetts/mcp-installer"
    ]
  }
  ```

### GitHub
- **Funktion**: GitHub Repository Management
- **Typische Anwendungen**: Versionskontrolle, Collaboration
- **Konfiguration**:
  ```json
  "server-github": {
    "command": "npx",
    "args": [
      "@modelcontextprotocol/server-github"
    ],
    "env": {
      "GITHUB_PERSONAL_ACCESS_TOKEN": "your-token-here"
    }
  }
  ```

### Shell Commander
- **Funktion**: Ausführung von Shell-Befehlen
- **Typische Anwendungen**: Automatisierung, Systemkonfiguration
- **Konfiguration**:
  ```json
  "Shell Commander": {
    "command": "npx",
    "args": [
      "-y",
      "@modelcontextprotocol/server-shell"
    ]
  }
  ```

### Memory
- **Funktion**: Erweiterter Speicher für Konversationen
- **Konfiguration**:
  ```json
  "Memory": {
    "command": "npx",
    "args": [
      "-y",
      "@modelcontextprotocol/server-memory"
    ]
  }
  ```

## Troubleshooting

### Problem 1: Server startet nicht nach Konfigurationsänderung

**Mögliche Ursachen:**
- Tippfehler in der Konfiguration
- Fehlende Berechtigungen
- Port bereits belegt

**Lösungen:**
- Überprüfe die Konfiguration auf Tippfehler
- Starte die App neu
- Prüfe die Portverfügbarkeit

### Problem 2: Installer schlägt fehl

**Mögliche Ursachen:**
- Netzwerkprobleme
- NPM-Registry nicht erreichbar
- Unzureichende Berechtigungen

**Hinweis:** Die Server werden automatisch nach dem Speichern der Konfiguration oder einem Neustart der App gestartet. Ein manueller Start ist nicht erforderlich.

### Problem 3: Dateisystem-Zugriff verweigert

**Mögliche Ursachen:**
- Fehlende Berechtigungen
- Falscher Pfad
- Datei/Verzeichnis existiert nicht

**Lösungen:**
- Überprüfe die Pfadangaben
- Stelle sicher, dass die Berechtigungen korrekt sind
- Erstelle fehlende Verzeichnisse

## Einrichtung Schritt für Schritt

### 1. Installation der Desktop-App

1. Lade die Claude Desktop-App herunter
2. Installiere die App
3. Starte die App und melde dich an

### 2. MCP-Server aktivieren

1. Öffne die Entwicklereinstellungen
2. Aktiviere die benötigten Server
3. Speichere die Einstellungen

### 3. Dateisystem-Zugriff einrichten

1. Öffne die Entwicklereinstellungen
2. Wenn der Server nicht läuft, klicke auf den "Konfiguration bearbeiten" Button
3. Füge die Filesystem-Konfiguration hinzu:

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem"
      ]
    }
  }
}
```

### 4. Projektverwaltung nutzen

Nach der Konfiguration des Filesystem-Servers kannst du in jeder Konversation auf lokale Dateien verweisen:

1. Erstelle ein Projektverzeichnis
2. Verweise auf Dateien mit relativem Pfad
3. Nutze die Dateisystem-Befehle

## Projekt-Prompt einrichten

Ein Projekt-Prompt kann in der kostenlosen Version für jede Konversation individuell eingerichtet werden. In der Desktop-App wird er automatisch in den Projekteinstellungen gespeichert:

1. Starte eine neue Konversation im Projekt
2. Klicke auf die drei Punkte (⋮) oben oder im Menü auf "Conversation"
3. Wähle "Custom Instructions" oder "Benutzerdefinierte Anweisungen"
4. Füge den Projekt-Prompt ein (siehe [Projekt-Prompt](claude-prompt.md))
5. Speichere die Einstellungen mit "Save"

**Hinweis:** In der kostenlosen Version muss der Projekt-Prompt für jede Konversation neu eingegeben werden. In der Desktop-App wird er automatisch in den Projekteinstellungen gespeichert.

## Nutzerpräferenzen konfigurieren

1. Öffne die App-Einstellungen
2. Wähle "Settings" oder "Einstellungen"
3. Gehe zu "User preferences" oder "Nutzerpräferenzen"
4. Trage deine Nutzerpräferenzen in den allgemeinen Claude-Einstellungen ein (siehe [Projekt-Prompt](claude-prompt.md))
5. Speichere die Einstellungen

## Versionsinformation

Diese Anleitung basiert auf der aktuellen Version der Claude Desktop-App. Da die Oberfläche und Funktionalität von Anthropic regelmäßig aktualisiert werden, können sich Einzelheiten ändern.