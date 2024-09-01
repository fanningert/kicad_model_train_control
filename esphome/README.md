# Model Train Control - ESPHome configuration examples

There is a non linear curve for the voltage control. On step line from 0 to 5V in the first 5% and then a linear line up to the input voltage. One side effect of DRV8871DDA.

Input voltage: 24V DC
| Percent | Output Voltage |
|---------|----------------|
| 0       | 0              |
| 10      | 6,5 V          |
| 20      | 8,6 V          |
| 30      | 10,7 V         |
| 40      | 12,6 V         |
| 50      | 14,6 V         |
| 60      | 16,5 V         |
| 70      | 18,4 V         |
| 80      | 20,1 V         |
| 90      | 22 V           |
| 100     | 24 V           |

For example, when you need 16V I selected 0,58 (58%) for the voltage_multi parameter.

## Templates

### Board

The central component for ESPHome usage. This create some internal components with unique IDs. When you stack the boards, you need to add one entry for every board with a unique board number.

Parameter:

* hub_no = every stack get it's unique id
* board_no = every board in the same stack get it's unique id

Usable output IDs like h1b1p1.
h = hub, b = board, p = Board Port

```yaml
packages:
  board1: !include
    file: common/mtc_ha_board.yaml
    vars:
      hub_no: 1
      board_no: 1
      i2c_address: "0x70"
  board2: !include
    file: common/mtc_ha_board.yaml
    vars:
      hub_no: 1
      board_no: 2
      i2c_address: "0x71"
```

### Power line

A simple H-Bridge to control the railway power of the train.

```yaml
packages:
  train01: !include
    file: common/mtc_ha_power_line.yaml
    vars:
      hub_no: ${hub_no}
      board_no: "1"
      port_no: "01"
      voltage_multi: 0.58
```

### Yield

```yaml
packages:
  yield01: !include
    file: common/mtc_ha_yield.yaml
    vars:
      hub_no: 1
      board_no: "1"
      port_no: "02"
      voltage_multi: 0.58
```

### Generic Switch

```yaml
packages:
  switch01: !include
    file: common/mtc_ha_switch.yaml
    vars:
      hub_no: 1
      board_no: "1"
      port_no: "03"
      voltage_multi: 0.58
```

### Signal

```yaml
packages:
  signal01: !include
    file: common/mtc_ha_signal.yaml
    vars:
      hub_no: 1
      board_no: "1"
      port_no: "04"
      voltage_multi: 0.58
```

### Decoupler

```yaml
packages:
  decoupler01: !include
    file: common/mtc_ha_decoupler.yaml
    vars:
      hub_no: 1
      board_no: "1"
      port_no: "05"
      voltage_multi: 0.58
```
