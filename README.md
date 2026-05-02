# city-infrastructure

**Urban and industrial infrastructure intelligence layer for the [ARCTURA Network](https://arctura.network).**

Coreweaver Labs' `city-infrastructure` module provides the physical infrastructure intelligence layer for **Operon** — the industrial intelligence subnet of the ARCTURA network. It delivers digital twin architecture for city-scale systems, IIoT sensor integration, and agentic automation across building management, utility networks, transportation, and wind farm operations.

This module powers **eXSeek™** wind farm optimization for Arctura Wind, running digital twins on Kafka telemetry routed through [blockmachine's](https://blockmachine.io) Bittensor-verified compute on SN19.

---

## Overview

```
city-infrastructure
├── Digital twin architecture for urban and industrial systems
├── IIoT sensor array management and telemetry ingestion
├── Kafka-native streaming pipeline → TimescaleDB
├── FastAPI backend for agent-facing and external APIs
├── 16-agent AURE cluster for autonomous system management
└── Bittensor-verified compute via blockmachine SN19
```

### Core capabilities

| Module | Description |
|---|---|
| **Digital Twins** | City-scale virtual replicas — energy grids, buildings, transport, utilities |
| **IIoT Integration** | Sensor array ingestion across building, utility, and wind infrastructure |
| **eXSeek™ Wind** | Turbine telemetry, RPM/power optimization, predictive maintenance |
| **Agentic Automation** | 16-agent AURE cluster for autonomous optimization and BFT verification |
| **Operon Contribution** | Physical infrastructure module for ARCTURA's industrial subnet |

---

## Architecture

```
                    ┌─────────────────────────────────┐
                    │        ARCTURA Network           │
                    │    arctura.network/operon        │
                    └────────────┬────────────────────┘
                                 │ Operon Subnet
                    ┌────────────▼────────────────────┐
                    │     city-infrastructure          │
                    │                                  │
          ┌─────────┴─────────┐        ┌──────────────┴──────┐
          │   Kafka Streams   │        │   AURE Agent Cluster │
          │  (telemetry bus)  │        │     16 agents        │
          └─────────┬─────────┘        └──────────────┬──────┘
                    │                                  │
          ┌─────────▼─────────┐        ┌──────────────▼──────┐
          │   TimescaleDB     │        │   Digital Twins      │
          │  (time-series)    │        │  (city-scale models) │
          └─────────┬─────────┘        └──────────────┬──────┘
                    │                                  │
          ┌─────────▼──────────────────────────────────▼──────┐
          │                   FastAPI                          │
          │          (agent API · external endpoints)          │
          └────────────────────────┬───────────────────────────┘
                                   │
          ┌────────────────────────▼───────────────────────────┐
          │         blockmachine SN19 — Bittensor compute       │
          │         BFT-verified · incentive-aligned            │
          └────────────────────────────────────────────────────┘
```

### Kafka topics

| Topic | Description |
|---|---|
| `city.energy.grid.readings` | Energy meter readings across grid nodes |
| `city.wind.exseek.telemetry` | Turbine RPM, power output, wind speed |
| `city.transport.flow.sensors` | Vehicle flow and road capacity data |
| `city.water.pressure.nodes` | Utility network pressure and flow |
| `city.building.hvac.status` | Building management and HVAC telemetry |
| `city.security.anomaly.detect` | Anomaly detection events across sectors |
| `city.utility.meter.readings` | kWh meter readings for billing/optimization |
| `operon.twin.sync.delta` | Digital twin fidelity and sync deltas |
| `operon.agent.actions` | AURE agent action log |
| `arctura.sn19.verified.batch` | Bittensor-verified compute batches from SN19 |

---

## Tech stack

| Layer | Technology |
|---|---|
| **Core language** | TypeScript · Python |
| **Streaming** | Apache Kafka |
| **Time-series DB** | TimescaleDB |
| **API** | FastAPI |
| **Orchestration** | Kubernetes · Docker |
| **Agent runtime** | AURE 16-agent architecture |
| **Blockchain compute** | Bittensor SN19 via blockmachine |
| **Frontend** | React · Next.js · Builder.io |
| **Network** | ARCTURA / Operon subnet |

---

## AURE Agent Cluster

The city-infrastructure module runs a 16-agent AURE cluster for fully autonomous operation. Each agent handles a specific system function:

| Agent | Role |
|---|---|
| `twin-sync` | Continuous digital twin fidelity synchronization |
| `energy-opt` | Grid load optimization and demand forecasting |
| `wind-forecast` | eXSeek™ turbine output prediction |
| `traffic-ctrl` | Transport flow optimization |
| `anomaly-det` | Cross-sector anomaly detection |
| `bft-verify` | Byzantine fault-tolerant consensus verification |
| `data-ingest` | Kafka consumer orchestration |
| `signal-proc` | Sensor signal processing and normalization |
| `pred-maint` | Predictive maintenance scheduling |
| `load-balance` | Agent workload distribution |
| `route-opt` | Logistics and transport route optimization |
| `sensor-val` | Sensor health validation |
| `emit-proof` | Cryptographic proof emission for SN19 |
| `mandate-enf` | Mandate chain enforcement |
| `geo-index` | Geospatial indexing of infrastructure nodes |
| `self-evolve` | Model self-improvement and adaptation |

Agents operate on the principle of **incentive alignment** — correct behavior is the economically optimal behavior, consistent with Bittensor's miner/validator model.

---

## Design principles

**01 — Verification over trust**
Every data payload, agent action, and system state is independently verifiable. No trust assumptions — cryptographic proof via BFT attestation or it didn't happen.

**02 — Incentive alignment**
Agent behavior follows economic incentives. Systems are designed so correct behavior is the profitable behavior, aligned with Bittensor's miner/validator model on SN19.

**03 — Physical-digital continuity**
The built environment and digital networks converge. City infrastructure, industrial systems, and blockchain compute are treated as one continuous layer — not separate domains.

**04 — Open by default**
All work is open-source unless a security constraint demands otherwise. The agentic web is built by people who share what they make.

---

## Getting started

### Prerequisites

- Node.js 20+ / Python 3.11+
- Docker + Kubernetes
- Apache Kafka
- TimescaleDB (PostgreSQL 15+)
- Access to blockmachine SN19 (for verified compute)

### Install

```bash
git clone https://github.com/CoreweaverLabs/city-infrastructure.git
cd city-infrastructure
npm install
```

### Environment

```bash
cp .env.example .env
```

Key environment variables:

```env
# Kafka
KAFKA_BROKERS=localhost:9092
KAFKA_GROUP_ID=city-infra-consumer

# TimescaleDB
TIMESCALE_URL=postgresql://user:pass@localhost:5432/city_infra

# Bittensor / blockmachine SN19
BITTENSOR_NETWORK=finney
SN19_VALIDATOR_ENDPOINT=https://api.blockmachine.io/sn19

# ARCTURA / Operon
OPERON_SUBNET_URL=https://arctura.network/operon
ARCTURA_API_KEY=your_key_here

# AURE Agent cluster
AURE_AGENT_COUNT=16
AURE_MANDATE_CHAIN=enforced
```

### Run

```bash
# Start the FastAPI backend
npm run api

# Start Kafka consumers
npm run ingest

# Start the AURE agent cluster
npm run agents

# Start the twin sync daemon
npm run twin-sync
```

### Docker

```bash
docker-compose up -d
```

---

## Operon integration

`city-infrastructure` is a named contributor to [Operon](https://arctura.network/operon), the industrial intelligence subnet of the ARCTURA network. The physical infrastructure and agentic systems layers built by Coreweaver Labs power Operon's IIoT capabilities, including integration with blockmachine's Bittensor-verified compute on SN19.

The module contributes:
- City-scale digital twin data and fidelity metrics
- IIoT telemetry streams via Kafka
- eXSeek™ wind farm optimization output for Arctura Wind
- BFT-attested agent actions via the `emit-proof` agent

---

## Related repos

| Repo | Description |
|---|---|
| [maelstrom](https://github.com/CoreweaverLabs/maelstrom) | TypeScript-native agentic UI infrastructure |
| [coreweaver-xyz](https://github.com/CoreweaverLabs/coreweaver-xyz) | Core identity and developer surface for the ecosystem |

---

## Network

- **ARCTURA Network** — [arctura.network](https://arctura.network)
- **Operon Subnet** — [arctura.network/operon](https://arctura.network/operon)
- **blockmachine SN19** — [blockmachine.io](https://blockmachine.io)
- **Arctura Wind** — [arcturawind.com](https://www.arcturawind.com)
- **AURE** — [au-re.org](https://au-re.org)

---

## License

MIT — © 2026 Coreweaver Labs.

Open-source under MIT. The agentic web is built by people who share what they make.

---

*Coreweaver Labs — Pioneering Decentralized Agentic AI. Contributor to Operon · ARCTURA Network · blockmachine SN19 · Bittensor.*
