# Docker Compose Stacks

A collection of Docker Compose templates designed for deployment with [Dokploy](https://dokploy.com/).

## Stacks

### [otel-lgtm](otel-lgtm/)

Grafana LGTM stack (Loki, Grafana, Tempo, Prometheus) with an embedded OpenTelemetry Collector. Receives traces, metrics, and logs via OTLP and stores them locally. Includes tail sampling and memory limiting. Connects to an external `dokploy-network`.

### [otel-collector](otel-collector/)

Standalone OpenTelemetry Collector (`contrib` distribution) that receives OTLP data and exports it to **New Relic**. Supports tail sampling for traces (errors + probabilistic) with memory limiting and health checks.

Copy `.env.example` to `.env` and set your `NEW_RELIC_LICENSE_KEY` before starting.

### [ollama](ollama/)

[Ollama](https://ollama.com/) inference server for running large language models locally. Includes an init container that automatically pulls `llama3.2:3b`, `gemma4:e4b`, and `gemma3:4b` models on first start. Connects to an external `dokploy-network`.

### [n8n](n8n/)

[n8n](https://n8n.io/) workflow automation platform. Configured with Europe/Warsaw timezone and secure cookies.

## Usage

Start any stack by navigating to its directory and running:

```bash
docker compose up -d
```

## License

[MIT](LICENSE)
