# 6. Mellow electronics and wiring

[Previous](05-toolhead.md) | [Guide index](../README.md) | [Next](07-klipper.md)

The confirmed mainboard is the **Mellow FLY-C5**. Confirm the toolhead board's exact model and PCB revision before selecting a diagram. Earlier project context mentions SHT36 V3, but this draft does not treat that as the final verified board identification.

Use [Mellow's C5 documentation](https://mellow.klipper.cn/en/docs/category/fly-c5/), [pinout](https://docs.3dmellow.com/en/docs/ProductDoc/MainBoard/fly-c/fly-c5/pin/), and [wiring reference](https://mellow.klipper.cn/en/docs/ProductDoc/MainBoard/fly-c/fly-c5/wiring/). Match them to the actual board revision. Manufacturer diagrams are linked rather than reproduced as an unverified custom pin map.

## Power and mounting

Disconnect mains, USB and any independent supplies before wiring. Mains work requires competent handling; keep terminals guarded and protective earth intact. Use correct strain relief, rated cable, appropriate overcurrent protection and connectors sized for each load. Do not tin stranded wire ends held by screw terminals; use properly crimped terminations suited to the terminal.

1. Inspect the donor PSU and record its output voltage, rating and condition.
2. Calculate the combined bed, hotend, electronics, motor and fan load, including warm-up load. Check PSU, board output and terminal ratings separately.
3. Mount the C5 and distribution hardware with ventilation and service access. Verify stand-off clearance beneath the boards.
4. Set driver and fan-voltage jumpers with all power disconnected. Match each fan's label; connector fit does not establish voltage.
5. Trace earth, line, neutral and DC wiring against the hardware documentation. Do not open or modify the PSU internally.

## Connection worksheet

Fill in actual connectors and pins after physically tracing each circuit. A signal name in this table is not a connector pin order.

| Circuit | Intended device | Required record before power |
| --- | --- | --- |
| Motion motors | C5 driver outputs | Motor role, port, driver type, phase pairs, rating and current |
| Extruder motor | Selected board/driver | Installed motor and port; direction and calibrated gearing |
| Bed heater | Rated power output | Heater rating, output rating, fuse and wire size |
| Bed sensor | Actual connected MCU input | Sensor model, MCU name, input and pull-up arrangement |
| Hotend heater | Chosen toolhead output | Heater voltage/wattage and board channel rating |
| Hotend sensor | Compatible temperature input | Exact sensor type, input and any required interface |
| Heatsink fan | Suitable fan output | Voltage, polarity and heater-fan behavior |
| Part cooling | Suitable fan output(s) | Voltage, polarity, shared-load rating and PWM behavior |
| Endstops / probe | Compatible input(s) | Logic voltage, pin order and polarity |
| CAN, if used | Host interface and nodes | CANH, CANL, reference/power connections and termination |

The bed sensor can be attached to a different MCU from the bed heater. Klipper's `sensor_pin` must name the MCU and pin where the sensor is actually connected; moving the heater output does not move the sensor input.

## CAN checks, if fitted

Use a line topology with short stubs and twisted CANH/CANL conductors. Use the same configured bitrate on all nodes. Terminate the two physical bus ends with 120-ohm resistors; do not enable termination on every board.

With **all power disconnected**, approximately 60 ohms between CANH and CANL is expected for two 120-ohm terminations in parallel. This is a termination check, not a complete wiring or insulation test. Confirm supply polarity and board connector order separately. See [Klipper CANBUS](https://www.klipper3d.org/CANBUS.html).

The final host-to-CAN arrangement is not yet established here. Do not assume C5 USB bridge firmware or a separate adapter without documenting the actual setup.

## First electrical inspection

1. Check for shorts and unintended contact to the frame with power disconnected.
2. Inspect crimps, terminal engagement, fuse ratings, protective earth, cable retention and polarity.
3. Keep heater loads disconnected for the initial logic bring-up, using an appropriate staged configuration. Connect temperature sensors and validate their readings first.
4. Shut down and disconnect all power before connecting heater loads or changing jumpers.
5. Test fans and sensors individually before enabling motion or heat.

**Gate:** connector worksheet complete, board revisions matched, supply/outputs within rating, sensor readings plausible and each channel positively identified.

**Photos to add:** `P12` C5 overview with readable labels, `P13` toolhead board and connector orientation, `P14` bed heater/sensor routing. Keep serial numbers, passwords and private network details out of published images.
