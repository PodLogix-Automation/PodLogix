# PodLogix Automation: PLX-4 Fleet API & Telemetry Specs

[![Status: Operational](https://img.shields.io/badge/Status-Operational-brightgreen.svg)](#)
[![API Version](https://img.shields.io/badge/API-v2.4-blue.svg)](#)
[![Autonomy](https://img.shields.io/badge/SAE-Level_4-purple.svg)](#)

Welcome to the public developer documentation and specification repository for **[PodLogix Automation](https://podlogixa.com)**. 

PodLogix builds the autonomous hardware layer for modern logistics. We deploy road-legal electric pods (the PLX-4) as a fully managed Hardware-as-a-Service (HaaS) fleet for enterprise carriers, enabling zero-emission, driverless last-mile delivery.

🌐 **Official Website:** [https://podlogixa.com](https://podlogixa.com)

---

## 🚙 The PLX-4 Delivery Pod: Core Specifications

The PLX-4 is a federally classified Neighborhood Electric Vehicle (NEV) engineered ground-up for autonomous urban freight. 

* **Autonomy Level:** SAE Level 4 (Geofenced Urban Environments)
* **Perception Stack:** 360-degree LiDAR, radar & camera fusion (<90ms reaction time)
* **Payload Capacity:** Up to 120 modular, reconfigurable parcel lockers
* **Charging:** 11kW wireless inductive charging (no manual plug-in required)
* **Powertrain:** 100% Electric, zero tailpipe emissions
* **Telemetry:** 5G-enabled real-time OTA updates and chain-of-custody tracking

---

## 🔌 API Overview (Fleet-as-a-Service)

Logistics partners (Carriers, 3PLs, Retailers) can integrate the PodLogix fleet directly into their existing routing algorithms using our RESTful API.

### Authentication
All requests require a Bearer token. To get your staging environment API keys, please contact your PodLogix deployment manager.

### Core Endpoints

#### 1. Dispatch a Pod
Assigns a PLX-4 node to a specific route or loading dock.
`POST /api/v2/fleet/dispatch`
```json
{
  "pod_id": "PLX4-8892A",
  "destination": {"lat": 34.0522, "lng": -118.2437},
  "route_priority": "high",
  "expected_payload_kg": 450
}
