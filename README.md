# Infrastructure (Docker Compose)

Local dev stack for the whole system.

Starts:

- Kafka + ZooKeeper (plus topic init)
- Redis
- Postgres (SensorManager)
- Postgres (Archiver)
- SensorManager, SensorSimulator, Archiver, Controller

## Branching

- `dev` – development
- `main` – stable / demo-ready

## Run

From the repo root:

```bash
docker compose -f infra/docker/docker-compose.yml up --build
```

Stop:

```bash
docker compose -f infra/docker/docker-compose.yml down
```

Clean state (wipe volumes):

```bash
docker compose -f infra/docker/docker-compose.yml down -v
```

## Ports (defaults)

- 8081 Archiver
- 8082 Controller
- 8083 SensorManager
- 8084 SensorSimulator
- 6379 Redis
- 9092 Kafka
