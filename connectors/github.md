# GitHub Connector
Repo: https://github.com/mgit0771/CLAUDE-APP

## Dostep
- User: mgit0771, Email: mg@fractals-ai.com
- Token: w credentials/github.env
- Clone: https://mgit0771:TOKEN@github.com/mgit0771/CLAUDE-APP
- SSH key VPS->GitHub: ~/.ssh/id_ed25519 na VPS

## Lokalnie
- Path: ~/Desktop/GIT-CLAUDE-APP/
- Branch: main

## Git workflow
- git add PLIK
- git commit -m opis
- git push
- UWAGA: credentials/ jest w .gitignore

## Struktura repo
- memory/core.md       - core identity i stan sesji
- connectors/          - opisy endpointow (ten folder)
- credentials/         - .gitignored - lokalne secrets
- vps-security/        - security scan i historia napraw
- context/             - snapshoty kontekstu
- skills/              - skill definitions

## GitHub API
- Base: https://api.github.com
- Auth: Authorization: token TOKEN