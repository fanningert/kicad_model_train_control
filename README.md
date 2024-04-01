# Model Train Control

Control unit for analog model trains, based on ESPHome. For visualation and controlling I using a Home Assistant instance.

```mermaid
flowchart LR
    Z[PowerSupply] ===|24V DC| A
    A[PCB_Power] ===|3.3V DC| B
    A === |16V DC| B
    B[PCB_Controller] -->|I2C| C
    B ===|3.3V| C
    B ===|16V| C
    C[PCB_Main] -->|GPIO| D
    C ===|16V| D
    D[PCB_HBridge]
```

## Parts

* pcb_hbridge - HBridge with is used as a three state switch or as a variable power control for the power line.
* pcb_main - Main pcb for the project 

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
