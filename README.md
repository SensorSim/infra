# SensorSim – Reactor Monitoring System

This repository contains infrastructure and deployment configuration.

## Repositories
- archiver – stores sensor measurements
- sensor-simulator – generates sensor data
- alarm-service – detects anomalies
- controller – API gateway and realtime data
- gui-app – Windows client

## Local run
```bash
docker compose -f docker/docker-compose.yml up
