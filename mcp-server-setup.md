# HANS' erweiterte Fähigkeiten - MCP Server Setup

Hey! Um dir noch besser helfen zu können, kannst du mich mit zusätzlichen Fähigkeiten ausstatten. Der MCP Server gibt mir Zugriff auf:
- Dateien und Code
- Webrecherche
- GitHub Integration
- Und vieles mehr!

## 🚀 Schnell-Setup

1. **Node.js installieren** (falls noch nicht vorhanden)
   - Lade Node.js von [nodejs.org](https://nodejs.org/)
   - Mindestens Version 18 empfohlen

2. **GitHub Personal Access Token erstellen**
   - Gehe zu [GitHub Settings > Developer Settings > Personal Access Tokens](https://github.com/settings/tokens)
   - Wähle "Tokens (classic)"
   - Klicke "Generate new token (classic)"
   - Setze folgende Berechtigungen:
     - `repo` (alle)
     - `workflow`
     - `write:packages`
     - `delete:packages`
   - Token kopieren und sicher aufbewahren!

3. **Umgebungsvariablen setzen**
   ```bash
   # Linux/macOS
   export GITHUB_TOKEN=dein_token_hier
   
   # Windows (PowerShell)
   $env:GITHUB_TOKEN="dein_token_hier"
   ```

4. **MCP Server installieren & starten**
   ```bash
   npx @anthropic-ai/mcp-server
   ```

## 🛠 Was ich damit alles kann

### 1. Dateizugriff
- Code lesen und schreiben
- Dateien erstellen und bearbeiten
- Verzeichnisse durchsuchen

### 2. GitHub Integration
- Repositories erstellen und verwalten
- Code committen und pushen
- Issues und PRs managen

### 3. Webrecherche
- Aktuelle Informationen finden
- Dokumentation durchsuchen
- Beispiele recherchieren

### 4. Entwicklungstools
- Terminal-Befehle ausführen
- Tests durchführen
- Debugging unterstützen

## 💡 Beispiele

### Code Review
```
"HANS, schau dir bitte diese Funktion an und gib mir Feedback zur Performance."
```

### Projekt Setup
```
"Lass uns ein neues React-Projekt aufsetzen und in GitHub hosten."
```

### Bug Fixing
```
"Ich habe hier einen Memory Leak. Kannst du die Logs analysieren?"
```

## ⚙️ Erweiterte Konfiguration

### Custom Port
```bash
npx @anthropic-ai/mcp-server --port 8080
```

### Eigenes SSL Zertifikat
```bash
npx @anthropic-ai/mcp-server --cert pfad/zu/cert.pem --key pfad/zu/key.pem
```

### Proxy Einstellungen
```bash
export HTTP_PROXY=http://proxy:port
export HTTPS_PROXY=http://proxy:port
```

## 🔧 Troubleshooting

### Port bereits in Verwendung
```bash
# Anderen Port verwenden
npx @anthropic-ai/mcp-server --port 8081

# Oder bestehenden Prozess beenden
lsof -i :3000  # Port-Nummer anpassen
kill -9 PID    # Gefundene PID verwenden
```

### GitHub Token Probleme
1. Token-Berechtigungen prüfen
2. Token neu generieren
3. Umgebungsvariable neu setzen

### Verbindungsprobleme
1. Firewall-Einstellungen prüfen
2. Proxy-Konfiguration überprüfen
3. SSL-Zertifikate validieren

## 📚 Weiterführende Links

- [Node.js Dokumentation](https://nodejs.org/docs)
- [GitHub REST API](https://docs.github.com/rest)
- [MCP Server GitHub](https://github.com/anthropics/mcp-server)

---
*Konfiguriert von HANS (Version 1.0.0) - Dein KI-Projektpartner mit Persönlichkeit* 🤓
