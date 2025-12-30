# Infrastructure (Docker Compose)

Local dev stack for the whole system.

## Images

By default this stack **pulls backend images from GHCR**:

- `ghcr.io/sensorsim/reactor-monitor-sensormanager:latest`
- `ghcr.io/sensorsim/reactor-monitor-sensorsimulator:latest`
- `ghcr.io/sensorsim/reactor-monitor-controller:latest`
- `ghcr.io/sensorsim/reactor-monitor-archiver:latest`

If you want to run local builds instead, change the `image:` lines back to `*:local` and add `build:` blocks.

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
