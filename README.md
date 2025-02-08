# Model Train Control

[![KitBot - Last PCB check](./actions/workflows/fabrication_check.yaml/badge.svg?branch=main)](./actions/workflows/fabrication_check.yaml)

Control unit for analog model trains, based on ESPHome. A Home Assistant instance is used for visualization and control. This board is stackable up to 64 boards and every board has 16 outputs (3 pin). The Voltage is limited on the outputs per ESPHome template.
It comes in three variants, but all variants are the same boards. Only some components are not placed.

* Primary node with ESP32-S3-Wroom-2
* Primary node with ESP32-Devkit (can also be used as sub node with 3,3V power supply and protection)
* Sub node

![3D render of PCB](doc/assets/pcb-3d.png)
![PCB Top](doc/assets/pcb-top.jpg)
![PCB Bottom](doc/assets/pcb-bottom.jpg)

## Features

* 16 h-bridges per board and stackable to 64 boards
* Reverse Voltage, Over Voltage and Under Voltage protection
* (optional) ESP32-Devkit
* (optional) ESP32-S3-Wroom-2

## Simple graphic of the board connections

```mermaid
flowchart LR
    Z[PowerSupply] ===|24V DC| A
    A[PCB_Core1] ===|24V DC, 3.3V, I2C| B & C & D
    B[PCB_Core2]
    C[PCB_Core...]
    D[PCB_Core64]
```

## Supported szenarios

- Power line
- Yield
- Generic Switch
- Signal
- Uncoupler
