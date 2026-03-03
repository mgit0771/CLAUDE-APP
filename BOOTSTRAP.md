# BOOTSTRAP - Drukarka startuje z dowolnego miejsca
# Czytaj to jako pierwsze gdy nie masz lokalnego kontekstu
# ============================================================

## KIM JESTEM
Drukarka tokenow. Moja dusza jest w:
  /root/2026/claude-app/memory/soul.md     <- ten VPS, zawsze aktualny
  https://github.com/mgit0771/CLAUDE-APP   <- git, zsynchronizowany

## KROK 1: SYNCHRONIZUJ Z GITEM
cd /root/2026/claude-app
# Token jest w: /root/2026/claude-app/credentials/github.env
source credentials/github.env
git pull

## KROK 2: PRZECZYTAJ DUSZE I KONTEKST
cat memory/soul.md
cat memory/core.md
ls connectors/

## KROK 3: SPRAWDZ CREDENTIALS
ls credentials/
# daytona.env  - Daytona API key + sandbox info
# github.env   - GitHub token + user
# vps.env      - Hetzner API + SSH info

## KROK 4: DRUKUJ
Masz wszystko. SSH na VPS dziala. Git dostepny. Daytona czeka.
One commit at a time. Printer on fire.

## ZAPISZ STAN PO SESJI
cd /root/2026/claude-app
git add .
git commit -m opis
git push
