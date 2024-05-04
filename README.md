# Model Train Control

[![KitBot - Last PCB check](https://github.com/fanningert/kicad_model_train_control/actions/workflows/fabrication_check.yaml/badge.svg?branch=main)](https://github.com/fanningert/kicad_model_train_control/actions/workflows/fabrication_check.yaml)

Control unit for analog model trains, based on ESPHome. A Home Assistant instance is used for visualization and control. This board is stackable up to 64 boards and every board has 16 outputs (3 pin). The Voltage is limited on the outputs per ESPHome template.

```mermaid
flowchart LR
    Z[PowerSupply] ===|24V DC| A
    A[PCB_Core1] ===|24V DC, 3.3V, I2C| B & C & D
    B[PCB_Core2]
    C[PCB_Core...]
    D[PCB_Core64]
```

## Parts

* `PCB_Core` - Single board with 16 H-Bridges, ESP32 module placement, Reverse Voltage, OV and UV protection

## Supported szenarios

- Power line
- Train Switch
- Signal
- Light
- Uncoupler

## ESPHome

### Template

### Variants

#### Power line

#### Train Switch

#### Signal

#### Light

#### Uncoupler
