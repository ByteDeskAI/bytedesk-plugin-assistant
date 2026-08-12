# bytedesk-plugin-assistant

Extracted **Assistant** process plugin for bytedesk-remote-gateway (ADR 0014).

Same plugin id (`assistant`) as the in-tree first-party surface. Install under
`GATEWAY_HOME/plugins/assistant/` and Control Bus `rescan` + `enable`. Host
authenticates before `/p/assistant/`. No gateway restart.

In-tree host routes (`/assistant`, `/assistant/api/*`) remain as stubs until this
package is the sole provider.

```bash
go build -o assistant ./cmd/assistant
go run github.com/ByteDeskAI/bytedesk-remote-gateway-plugin-sdk/cmd/plugin-sdk@v0.1.0 validate --dir .
go run github.com/ByteDeskAI/bytedesk-remote-gateway-plugin-sdk/cmd/plugin-sdk@v0.1.0 pack --dir . --out dist
```
