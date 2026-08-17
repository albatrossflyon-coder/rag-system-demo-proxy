# rag-system demo proxy

Isolated deployment of [CLIProxyAPI](https://github.com/router-for-me/CLIProxyAPI) that translates
Anthropic Messages API calls into OpenRouter's free-tier `nvidia/nemotron-nano-9b-v2:free` model.

Exists only to power rag-system's public `/demo/ask` endpoint. Runs on its own dedicated OpenRouter
API key, isolated from any other Albatross AI tool/deployment, so public demo traffic can never affect
another service's quota.

Source is a clean copy of CLIProxyAPI's `cmd/`, `internal/`, `sdk/`, `static/` with a minimal,
single-route `config.yaml` (this repo's own inbound auth key + the one OpenRouter route above) --
not a fork tracking upstream.
