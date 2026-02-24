# VPS Security Scan Report
Date: 2026-02-25
Server: claude-app-vps (128.140.75.166, nbg1, cpx22)

## CRITICAL

### 1. DYSK 100% ZAPELNIONY
- /dev/sda1 - 38GB / 38GB uzyte
- Skutek: PostgreSQL nie moze sie uruchomic
- Akcja: natychmiastowe czyszczenie

### 2. HARDCODED API KEY w gemini_drive_bridge/app.py
- SECRET_API_KEY wbity na twardo w kod
- credentials.json i token.json w tym samym katalogu
- Akcja: rotacja klucza, przeniesienie do env vars

### 3. PORTY BEZ AUTENTYKACJI
- :8765 OpenMemory MCP (brak auth)
- :6333 Qdrant vector DB (brak auth)
- :3001 OpenMemory UI (brak auth)

## HIGH

### 4. BRAK FIREWALLA
- UFW nieaktywny, brak Hetzner Cloud Firewall
- Wszystkie porty otwarte na swiat

### 5. WRAZLIWE PLIKI W /root
- gcloud_sa_key.json - Google Cloud Service Account key
- gog_creds.json / gog_creds.b64
- credentials.json i token.json w gemini_drive_bridge

### 6. STARY STACK
- /root/replit 7.7GB
- Wiele starych skryptow, backupow, logow

## OK
- Tylko 1 klucz SSH (po czyszczeniu)
- SSH na porcie 22
- Docker dziala poprawnie
- Siec stabilna po netplan fix (enp1s0 nie eth0)
