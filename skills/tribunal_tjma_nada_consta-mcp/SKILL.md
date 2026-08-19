---
name: tribunal_tjma_nada_consta-mcp
description: Skill da REST API do Tribunal TJMA: Nada Consta na MCP.AI: 1 endpoint em /api/tribunal_tjma_nada_consta. Tribunal TJMA: Nada Consta, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Tribunal TJMA: Nada Consta — REST API skill

Você tem acesso à **Tribunal TJMA: Nada Consta** REST API na MCP.AI.

> Tribunal TJMA: Nada Consta, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/tribunal_tjma_nada_consta
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/tribunal_tjma_nada_consta/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"instancia":"...","natureza":"...","cpf":"...","nome":"...","birthdate":"...","nome_mae":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/tribunal_tjma_nada_consta/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `tribunal_tjma_nada_consta_consultar`

Tribunal TJMA: Nada Consta, consulta em fonte oficial. _(POST /api/tribunal_tjma_nada_consta/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `instancia` | string | Sim | Parâmetro de consulta "instancia". |
| `natureza` | string | Sim | Parâmetro de consulta "natureza". |
| `cpf` | string | Sim | Parâmetro de consulta "cpf". |
| `nome` | string | Sim | Parâmetro de consulta "nome". |
| `birthdate` | string | Sim | Parâmetro de consulta "birthdate". |
| `nome_mae` | string | Sim | Parâmetro de consulta "nome_mae". |
| `nome_pai` | string | Não | Parâmetro de consulta "nome_pai". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_tribunal_tjma_nada_consta` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
