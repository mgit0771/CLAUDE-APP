# CLAUDE-APP

Persistence & context connector dla Claude App (claude.ai / Claude Desktop).

## Koncepcja

LLM to drukarka tokenów. Kontekst to instrukcja drukowania.
To repo jest zewnętrzną pamięcią — SSOT dla sesji Claude.

## Struktura

- `context/` — snapshoty kontekstu sesji
- `skills/` — zdefiniowane skille i narzędzia  
- `memory/` — persystentna pamięć między sesjami
- `connectors/` — konektory do zewnętrznych endpointów (Spotify, GitHub, etc.)

## Flow

1. Nowa sesja → wczytaj `memory/core.md` jako pierwszy kontekst
2. W trakcie sesji → commituj kluczowe ustalenia
3. Przed kompaktacją → dump stanu do `context/snapshot.md`
