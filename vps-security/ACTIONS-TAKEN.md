# Actions Taken - VPS Security Hardening
Date: 2026-02-25

## Zrobione

### Dysk - zwolniono ~4GB
- Usunieto: google-cloud-cli tar.gz, google-cloud-sdk.tar.gz, qwen backupy
- Usunieto: QWEN-CODE-FINAL-13.08.25, qwen-code-final-snapshot
- Usunieto: qwen-code, open-interpreter-env, opencodetmp, gemini_2025
- Docker system prune: +444MB
- Wynik: 98% -> 91% (3.3GB wolnego)

### SSH
- Usunieto 5 starych kluczy z authorized_keys
- Zostaje tylko: claude-app-vps (ed25519)

### Hetzner Cloud Firewall (ID: 10589431)
Nazwa: claude-app-firewall
Reguly IN (reszta BLOCK):
- 22/tcp SSH
- 8765/tcp OpenMemory MCP
- 5001/tcp Gemini Drive Bridge
- 3001/tcp OpenMemory UI
Reguly OUT: all allowed

### OpenMemory Stack
- Postgres wstal po zwolnieniu miejsca
- Wszystkie 4 kontenery UP

## Do zrobienia

- Zrotowac SECRET_API_KEY w gemini_drive_bridge/app.py
- Przeniesc credentials do .env
- Sprawdzic gcloud_sa_key.json
- Dalsze czyszczenie dysku (replit 7.7GB)
- Rozwazyc ograniczenie portow 8765/3001 do trusted IPs
- Ustawic monitoring dysku (alert przy >85%)
