# Infrastructure (Docker Compose)

Everything needed for local development is under `infra/docker`.

## What gets started

- Kafka + Zookeeper
- Kafka init container (creates topics)
- Redis
- Postgres for SensorManager (`postgres-sensormanager`)
- Postgres for Archiver (`postgres-archiver`)
- The 4 microservices

## Commands

Build + start:
```bash
cd infra/docker
docker compose build
docker compose up -d
```

Stop:
```bash
cd infra/docker
docker compose down
```

Stop + wipe databases:
```bash
cd infra/docker
docker compose down -v
```

## Ports

- 8081 Archiver
- 8082 Controller
- 8083 SensorManager
- 8084 SensorSimulator
- 5432/5433 Postgres (internal in compose; host mapping depends on compose)
- 6379 Redis
- 9092 Kafka
