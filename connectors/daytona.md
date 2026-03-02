# Daytona Connector
Cloud sandboxes - izolowane srodowiska dev z pelna persystencja

## Dostep
- CLI: przez SSH na VPS -> daytona sandbox list
- Toolbox API: https://proxy.app.daytona.io/toolbox/{SANDBOX_ID}/process/execute
- Token + pelne info: credentials/daytona.env
- Docs: https://docs.daytona.io

## Aktywny sandbox: claude-playground
- ID: 8b9de040-ade9-4388-a67e-c3a3dc582138
- Spec: 1 CPU, 1GB RAM, 3GB disk, user: daytona
- Python 3.13.3, Node 24.3.0, pip 25.0.1
- auto-stop: 60 min

## Toolbox API - exec bezposrednio z Maka
- POST https://proxy.app.daytona.io/toolbox/{ID}/process/execute
- Header: Authorization: Bearer TOKEN
- Body JSON: {command: STRING}
- Response: {result: STRING, exitCode: 0}

## Komendy CLI (przez SSH na VPS)
- daytona sandbox list
- daytona sandbox create --name NAME --class small --target eu --auto-stop 60
- daytona sandbox start/stop/delete NAME
- daytona sandbox exec NAME -- COMMAND
- daytona ssh NAME

## Limity sieci (free tier)
- Dostep do rejestr—w pakietow: npm, pip, apt OK
- Ogolny internet: ZABLOKOWANY (wymaga Tier 3/4 platny)

## Inne sandboxes
- infra-bunker STOPPED ID: 1d1595e7-b2e2-4a8a-ae85-70074722e382
- openclaw-* ARCHIVED - stare projekty