# JADE — Smart Home IoT Dashboard with LLM Control

JADE is a **Raspberry Pi–centric smart home automation network** built to unify multiple in-house IoT peripherals through a single control layer. It uses **MQTT** for lightweight device messaging, **Node-RED** for orchestration and dashboard logic, and API-based **LLM integration** for natural-language control of connected devices. [web:100][web:103][web:113]

## Overview

The goal of JADE was to create a **modular, extensible, and locally controllable home automation platform** that could:
- Manage multiple custom IoT nodes from one dashboard.
- Support **real-time device communication** using MQTT.
- Enable **voice and natural-language interaction** through an LLM.
- Serve as a foundation for future smart-home peripherals and automation routines. [web:102][web:106]

Unlike isolated IoT prototypes, JADE was designed as a **central hub architecture**, where the Raspberry Pi acts as the primary coordinator and peripheral devices plug into a shared messaging ecosystem. MQTT’s publish-subscribe model is especially well suited for this kind of modular smart-home system. [web:106][web:107]

## Features

- **Centralized dashboard** using Node-RED for monitoring and control. [web:101][web:103]
- **MQTT-based communication** between devices and the Raspberry Pi hub for lightweight, low-latency messaging. [web:100][web:113]
- **Modular device integration**, allowing custom peripherals to be added without redesigning the whole system. [web:106]
- **LLM-powered voice assistant** for natural-language control of home automation commands.
- **Edge-oriented architecture** centered on a Raspberry Pi for local orchestration.
- **Expandable ecosystem** designed to work with companion modules such as audio, switching, and sensing peripherals.

## System Architecture

JADE follows a **hub-and-node architecture**:

1. **Raspberry Pi 3** acts as the central controller.
2. **MQTT broker** handles communication between devices.
3. **Node-RED dashboard** provides visual flows, control logic, and automation.
4. **Custom IoT peripherals** publish status updates and subscribe to commands.
5. **LLM integration layer** converts natural-language requests into actionable control commands.

### Core Components

- **Hub:** Raspberry Pi 3
- **Messaging Layer:** MQTT
- **Orchestration / Dashboard:** Node-RED
- **Device Firmware:** MicroPython / C
- **AI Layer:** API-integrated LLM assistant

## Connected Modules

JADE was built as a one-stop platform for multiple in-house devices, including:

- **FLORA** — Wi-Fi-based switch array for appliance control.
- **VERA** — Wi-Fi/BLE-based smart home audio system.
- Additional custom peripherals connected through the same MQTT-controlled architecture.

## Tech Stack

- **Hardware:** Raspberry Pi 3, ESP-based IoT peripherals
- **Languages:** Python, C, MicroPython
- **Protocols:** MQTT
- **Frameworks / Tools:** Node-RED
- **AI Integration:** LLM API for voice / natural-language command handling

## How It Works

A typical JADE interaction flow looks like this:

1. A user opens the dashboard or speaks a command.
2. The dashboard or LLM layer interprets the request.
3. JADE publishes the relevant control message over MQTT.
4. The target peripheral subscribes to the topic and executes the action.
5. Status or sensor data is sent back to the hub for monitoring and display. [web:106][web:113]

This architecture keeps the system **scalable**, because new devices can be integrated by assigning new topics and Node-RED flows instead of redesigning the control stack. [web:106][web:113]

## Repository Structure

```bash
JADE/
├── dashboard/          # Node-RED flows / dashboard configs
├── peripherals/        # Device-side code for custom IoT modules
├── mqtt/               # Broker or topic configuration
├── llm-integration/    # Voice / natural-language control layer
├── docs/               # Architecture diagrams, notes, screenshots
└── README.md
```

> Adjust the structure above to match the actual repo layout if needed.

## Setup

### Prerequisites

- Raspberry Pi 3 or later
- Python installed
- MQTT broker (Mosquitto or equivalent)
- Node-RED installed on Raspberry Pi
- Network-connected IoT peripherals
- API key or endpoint for the LLM integration layer

### Installation

1. Clone the repository:
```bash
git clone https://github.com/Ash29062/JADE.git
cd JADE
```

2. Set up the MQTT broker.

3. Start Node-RED on the Raspberry Pi.

4. Configure connected devices to publish/subscribe to the correct MQTT topics.

5. Add your LLM API credentials to the assistant configuration.

6. Launch the dashboard and test control flows.

## Example Use Cases

- Turn appliances on or off from a dashboard.
- Trigger actions using **voice or natural-language commands**.
- Monitor device states from a single hub.
- Expand the home network by plugging in new MQTT-enabled modules.

## Design Goals

JADE was built with the following priorities:

- **Modularity** — easy to add new devices.
- **Low-latency communication** — lightweight MQTT messaging. [web:100][web:113]
- **Human-friendly control** — dashboard + voice interaction.
- **Local-first orchestration** — Raspberry Pi as a deployable edge hub.
- **Scalability** — suitable for extending into a larger home automation ecosystem. [web:106]

## Future Improvements

- Add authentication and secure device provisioning.
- Log telemetry and device activity over time.
- Add rule-based automation for scheduled tasks.
- Expand LLM support for contextual multi-step commands.
- Build a richer front-end dashboard for mobile use.

## Motivation

JADE was created to move beyond isolated IoT demos and build a **cohesive smart-home platform** where embedded devices, dashboards, and AI-based interfaces work together in a single system. It demonstrates practical integration across **IoT networking**, **edge systems**, and **applied AI**.

## License

This project is licensed under the MIT License unless stated otherwise.
