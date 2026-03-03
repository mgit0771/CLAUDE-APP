# Mapify Connector
Mind maps z AI - text/YouTube/PDF/URL -> mapa mysli

## CREDENTIALS (czekam na API key)
MAPIFY_API_KEY=???
# Zdobadz: https://mapify.so -> Settings -> API Keys -> Generate

## BASE
URL:  https://api.mapify.ai/v1/
Auth: Authorization: Bearer API_KEY
Content-Type: application/json

## KLUCZOWE ENDPOINTY
POST   /v1/maps          - stworz mape
GET    /v1/maps          - lista map
GET    /v1/maps/{id}     - pobierz mape
PUT    /v1/maps/{id}     - edytuj mape
DELETE /v1/maps/{id}     - usun mape

## TWORZENIE MAPY Z TEKSTU
curl -s -X POST https://api.mapify.ai/v1/maps
  -H 'Authorization: Bearer API_KEY'
  -H 'Content-Type: application/json'
  -d '{title: Moja mapa, content: # Temat
## Podtemat 1
## Podtemat 2}'

## TWORZENIE MAPY Z YOUTUBE
-d '{url: https://youtube.com/watch?v=XXX}'

## RESPONSE ZAWIERA
edit_url   - link do edycji w web UI
share_url  - link do udostepniania
preview    - URL do obrazka podgladowego

## CO MOZNA PRZETWORZYC
- Plain text / Markdown
- YouTube URL
- PDF, Word, PowerPoint
- Web articles (URL)
- 30+ jezykow (parametr language: pl dla polskiego)

## MCP SERVER (dla agentow)
npm: @xmindltd/mapify-mcp-server
claude_desktop_config.json:
  {mcpServers: {mapify: {command: npx, args: [-y, @xmindltd/mapify-mcp-server], env: {MAPIFY_API_KEY: KEY}}}}

## USE CASES
- Research / artykul -> mapa konceptow
- Notatki ze spotkania -> mapa z action items
- YouTube tutorial -> mapa nauki
- Stack technologiczny -> mapa architektury
- Sesja z drukarka -> mapa wynikow

## DOCS
API Ref:  https://api.mapify.ai/docs/
Blog MCP: https://mapify.so/blog/introducing-mapify-mcp-server
Zapier:   https://mapify.so/blog/how-to-automate-mind-map-creation-zapier-mapify
NPM:      https://www.npmjs.com/package/@xmindltd/mapify-mcp-server

## GOTCHAS
- Sprawdz rate limit headers: X-RateLimit-*
- edit_url i share_url z response sa kluczowe - zapisuj je
- API docs moze wymagac logowania przez przegladarke
- Zacznij od malych prostych map, potem skaluj