# VPS Connector
Hetzner Cloud VPS - glowny hub infrastruktury

## Dostep
- SSH: root@128.140.75.166, klucz: credentials/claude_app_vps
- Alias: vps3 w ~/.zshrc na Maku
- Pelne info + API token: credentials/vps.env

## Spec
- cpx22: 2 vCPU, 4GB RAM, 38GB SSD, nbg1 Nuremberg
- OS: Ubuntu 24 (snapshot: ubuntu-4gb-fsn1-2-23022026)
- Dysk: ~68%, 12GB wolne

## Aktywne uslugi
- 22/tcp SSH (zawsze)
- Docker: WYLACZONY (disabled)
- Glances: localhost:61209

## Hetzner API
- Base: https://api.hetzner.cloud/v1
- Server ID: 122021501
- Firewall ID: 10589431 (otwarte: 22, 8765, 5001, 3001)
- Docs: https://docs.hetzner.cloud
- Token: w credentials/vps.env

## Narzedzia na VPS
- Daytona CLI v0.144.1 /usr/local/bin/daytona
- Docker + containerd (disabled, mozna wlaczyc)
- Python 3, git, curl