# 5. Dragon Burner and ALPS Ultra HF

[Previous](04-corexz.md) | [Guide index](../README.md) | [Next](06-electronics.md)

## Choose a complete compatible toolhead set

The project's toolhead is **Dragon Burner**, not the Stealthburner supplied in the Trinity archive. Use [chirpy2605's Dragon Burner documentation](https://github.com/chirpy2605/voron/tree/main/V0/Dragon_Burner) and its linked configurator to select a matching cowl, hotend mount, extruder mount, carriage interface and PCB mount.

The upstream design offers Switchwire mounting options, but that alone does not verify a fit to this Trinity carriage or ALPS assembly. Record the exact adapter and revision used here.

| Interface | What must be checked |
| --- | --- |
| X carriage to Dragon Burner | Hole pattern, screw length, belt clamps and rail clearance |
| ALPS hotend to printed mount | Exact SKU, mounting faces, nozzle height, heater and sensor exits |
| Extruder to hotend | Mount pattern, filament alignment, guide length and motor clearance |
| Toolhead board to mount | PCB revision, connector access, driver cooling and cable retention |
| Fans to ducts | Size, voltage, polarity, inlet clearance and duct/nozzle position |
| Probe to carriage | Detection range, wiring, offsets and bed coverage |

**ALPS is not enough to identify the sensor configuration.** Confirm whether the installed hotend includes a pressure-based leveling module, and whether that module is actually used. A pressure sensor, an eddy probe and a mechanical Z switch are different systems. Do not connect or configure them interchangeably.

## Assembly sequence

1. Dry-fit the carriage adapter on the X carriage. Check access to rail screws and belt clamps.
2. Install the specified heat-set inserts in the selected Dragon Burner parts. Allow them to cool before fitting screws.
3. Fit the hotend using its manufacturer's mounting instructions. Inspect heater and temperature-sensor retention.
4. Assemble and mount the chosen extruder. Confirm a straight filament path and use only the guide-tube length required by that combination.
5. Install the heatsink fan and part-cooling fans with their intended airflow directions. Keep wires out of impellers and mounting faces.
6. Install the cowl and ducts. Check nozzle projection and clearance to the build surface before powering the machine.
7. Mount the toolhead board using insulated clearance where required; no conductive parts may contact unintended PCB pads.
8. Add harness strain relief at the toolhead and frame. Verify the harness can follow full X and Z motion without pulling connectors.

Do not hot-tighten an unidentified ALPS hotend using a generic temperature or torque. Use instructions for the exact installed hotend and nozzle.

## Clearance check

With power disconnected and the gantry supported, inspect the leftmost/rightmost X positions and low/high Z positions. Include the board plugs, extruder motor, ducts, bed clips, belt ends and probe. The nozzle must reach the intended bed area while the cowl remains clear. Recalculate printable travel and probe mesh bounds for this assembly.

**Gate:** exact hotend and sensor recorded, adapter mechanically verified, filament path clear, fans unobstructed, wiring retained and movement envelope checked.

**Photos to add:** `P09` front/side nozzle and duct alignment, `P10` rear adapter and PCB mount, `P11` labels for hotend, heater, sensor and fans.
