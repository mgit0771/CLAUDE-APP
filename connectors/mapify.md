# Mapify Connector
Mind maps z AI - prompt/YouTube/website -> mapa mysli
mapify.so (XMind Ltd) - NIE mylic z mapify.ai (GIS platform!)

## CREDENTIALS
MAPIFY_API_KEY=8be37272cad33b1a2487915b9347082de588e6910e387ef62a97bb8870ca6a9e
# Pelne info: credentials/mapify.env

## PRAWDZIWY ENDPOINT (znaleziony w NPM source)
POST https://mapify.so/api/v1/preview-mind-maps
Header: Authorization: Bearer API_KEY
Header: Content-Type: application/json

## BODY
{
  prompt:   TEKST lub URL (dla youtube/website),
  mode:     prompt / ai-search / youtube / website,
  language: pl / en / ... ,
  from:     mcp
}

## RESPONSE
{
  code: 0,
  data: {
    image:    URL do obrazka PNG mapy,
    continual: URL do edycji w web UI,
    mode:     uzyty mode,
    width/height: wymiary obrazka
  }
}

## PRZYKLADY

# Z tekstu/promptu:
curl -s -X POST https://mapify.so/api/v1/preview-mind-maps
  -H Authorization: Bearer KEY
  -H Content-Type: application/json
  -d {prompt: Temat mapy, mode: prompt, language: pl, from: mcp}

# Z YouTube:
  -d {prompt: https://youtube.com/watch?v=XXX, mode: youtube, language: pl, from: mcp}

# Z URL strony:
  -d {prompt: https://example.com/article, mode: website, language: pl, from: mcp}

# AI search (mapify sam szuka info):
  -d {prompt: Agentic Engineering 2026, mode: ai-search, language: pl, from: mcp}

## UWAGI
- api.mapify.ai to INNY serwis (GIS/geospatial) - nie uzywac!
- Prawdziwy endpoint znaleziony w kodzie NPM @xmindltd/mapify-mcp-server
- image URL to podglad PNG - mozna go embedowac/pokazac
- continual URL to link do edycji w web UI mapify.so

## DOCS
MCP blog:  https://mapify.so/blog/introducing-mapify-mcp-server
NPM:       https://www.npmjs.com/package/@xmindltd/mapify-mcp-server
API docs:  https://api.mapify.ai/docs/ (GIS - inna platforma!)