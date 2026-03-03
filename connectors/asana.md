# Asana Connector
Cloud PM - tasks, projects, webhooks, agenty

## CREDENTIALS (jeszcze nie mam - czekam na PAT + workspace_gid)
ASANA_PAT=2/1213168200814906/1213504091750932:d33f58a5a8c996d6d510b385dd64f65a
ASANA_WORKSPACE_GID=1213168200814919
# Token: https://app.asana.com/0/my-apps -> Personal Access Token

## BASE
URL:  https://app.asana.com/api/1.0/
Auth: Authorization: Bearer PAT
Content-Type: application/json

## KLUCZOWE ENDPOINTY

# Kim jestem / workspace info:
GET /users/me
GET /workspaces

# Projekty:
GET /projects?workspace=WORKSPACE_GID
POST /projects
GET /projects/PROJECT_GID/tasks

# Taski:
POST /tasks
GET /tasks/TASK_GID
PUT /tasks/TASK_GID
GET /workspaces/WORKSPACE_GID/tasks/search

# Sekcje:
POST /projects/PROJECT_GID/sections
POST /tasks/TASK_GID/addProject   # body: {data:{project:X, section:Y}}

# Custom fields:
POST /workspaces/WORKSPACE_GID/custom_fields
PUT /tasks/TASK_GID   # body: {data:{custom_fields:{FIELD_GID: value}}}

# Webhooks:
POST /webhooks   # body: {data:{resource:GID, target:URL}}
GET /webhooks?workspace=WORKSPACE_GID

# Komentarze/Stories:
POST /tasks/TASK_GID/stories

## TYPOWY PATTERN
curl -s -X POST https://app.asana.com/api/1.0/tasks
  -H 'Authorization: Bearer PAT'
  -H 'Content-Type: application/json'
  -d '{data:{name:Zadanie,workspace:WORKSPACE_GID,projects:[PROJECT_GID]}}'

## MCP SERVER (dla agentow z MCP)
Official V2: https://developers.asana.com/docs/mcp-server
Claude MCP URL: jesli podlaczony - sprawdz w connectors sesji

## PYTHON SDK
pip install asana
import asana
client = asana.Client.access_token(PAT)
tasks = client.tasks.find_all({'workspace': WORKSPACE_GID})

## NODE SDK
npm install asana
const asana = require('asana')
const client = asana.Client.create().useAccessToken(PAT)

## DOCS
API Ref:    https://developers.asana.com/docs/asana
Explorer:   https://developers.asana.com/explorer
Webhooks:   https://developers.asana.com/docs/webhooks
Rate limits: https://developers.asana.com/docs/rate-limits
Errors:     https://developers.asana.com/docs/errors
MCP V2:     https://developers.asana.com/docs/mcp-server

## GOTCHAS
- Wszystkie body opakowac w {data: {...}}
- Workspace GID potrzebny do prawie wszystkiego - pobierz przez GET /workspaces
- Rate limit: 1500 req/min dla Premium, 150 dla Free
- Pagination: offset token w response gdy wiecej niz limit rekordow
- Webhook wymaga publicznego URL do handshake (nie localhost)
## MY TASKS LIST GID
1213168204011058

## SEKCJE MY TASKS
Ostatnio przypisane - inbox (55 taskow)
!                   - priorytety (10 taskow)
LETTA               - (13 taskow)
WORKFLOW            - (5 taskow)
OPERATIONS          - (4 taskow)
GIT, TEST, CHECK, SKILLS/CLIs, LEARN/READ, CC, ANTIGRAVITY

## PROJEKTY
GMAIL MASTER      GID: 1213381145137839
PERPLEXITY-SPACE  GID: 1213503045487533
