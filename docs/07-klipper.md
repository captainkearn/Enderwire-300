# 7. Klipper setup and first commissioning

[Previous](06-electronics.md) | [Guide index](../README.md) | [Next](08-troubleshooting.md)

No flashable firmware or runnable `printer.cfg` is supplied in this draft. The existing local H2V2S configuration bundle describes a different setup and has not been adopted as an Enderwire 300 configuration.

Start with the firmware target and bootloader instructions for each exact Mellow PCB revision. Match firmware, bootloader offsets, crystal and communication transport; do not guess settings from a similar board. Back up working configurations before updating firmware or host packages.

## Configuration decisions

| Area | Required Enderwire 300 decision |
| --- | --- |
| Kinematics | `corexz` for the completed CoreXZ mechanism |
| Main MCU | Actual C5 USB serial or CAN UUID and transport |
| Toolhead MCU | Actual board identity, firmware and transport |
| Motion | Motor-to-driver map, direction, pulley tooth count and belt pitch |
| Rotation distance | For a direct belt pulley, belt pitch times pulley teeth; account for gearing if present |
| Current | Motor and driver ratings, cooling and observed thermal behavior |
| Travel | Measured safe mechanical limits and nozzle coverage |
| Homing | Physical switches or a validated sensorless strategy for each axis |
| Z reference | Actual endstop/probe and safe homing location |
| Heaters | Correct output, sensor model/input, limits and PID tuning |
| Extruder | Actual gearing, motor, rotation distance and thermal limits |
| Fans | Actual board pins, voltage and automatic hotend cooling |

Mellow's generic reference config illustrates board pins; its example travel, Z rotation distance, temperature limits and heater controls are not this build's settings.

## Gate A: communication and temperature

1. Bring up the selected host and each MCU using the matching Mellow instructions. Record firmware versions and transport identities privately.
2. Check communication without heater loads enabled. Correct MCU names in all remote pin references.
3. Confirm bed and hotend sensors report believable, stable ambient temperatures. Gently warming a sensor by hand should affect the corresponding reading.
4. Test `M112` and recovery using Klipper's [configuration checks](https://www.klipper3d.org/Config_checks.html). Also keep the physical power switch accessible.

Stop on missing, implausible or rising temperatures. Do not widen temperature limits to suppress a sensor fault.

## Gate B: endstops and motors

1. Keep the gantry supported and move the mechanism away from hard stops with power off. Restore power only after checking clearances.
2. For physical switches, use `QUERY_ENDSTOPS` while released and manually actuated; every switch must change state correctly.
3. Validate a probe's state and detection behavior with ample nozzle clearance using that probe's own procedure. Do not assume ALPS nozzle sensing is enabled just because the hotend supports it.
4. Use the Klipper motor-check procedure with room for motion. CoreXZ motor buzz can move both X and Z; treat the two motors as a coupled system.
5. Verify motor wiring, belt route and directions together. Do not fix a mechanically incorrect route by randomly inverting pins.

For sensorless homing, first identify the installed driver and the correct C5 DIAG signal/jumper. Follow [Klipper's TMC driver guidance](https://www.klipper3d.org/TMC_Drivers.html). A static virtual-endstop query is not equivalent to testing a mechanical switch, and a stall value alone does not prove successful homing. Tune one intended homing move at a time. Do not assume a sensorless Z strategy is established for this build.

## Gate C: homing and travel

Test individual axes at conservative speed with an immediate stop available. For a verified physical X/Y endstop setup, test X and Y separately before any combined home. Validate the chosen Z mechanism and required XY homing/probe position before its first descent. Never begin commissioning with an unverified `G28` of all axes.

After reliable homing, approach each boundary in small controlled moves. Record safe X/Y/Z limits, probe reach, cable limits and nozzle coverage. Keep margins from rail ends and hard stops. Establish mesh bounds from probe coverage, not bed dimensions.

## Gate D: heat and calibration

1. Power down before connecting heater loads. Verify outputs and matching sensors once more.
2. Following Klipper's heater checks, command a low initial target for one heater, watch that sensor rise, turn it off and confirm cooling. Test the other heater separately. Stop immediately if the wrong channel responds.
3. Confirm automatic heatsink cooling and test part cooling independently.
4. PID-tune each heater using a suitable temperature within the confirmed assembly's limits, with normal fans and sock fitted. Save the results.
5. Establish bed tramming, the chosen Z offset/reference and repeatable probing before making a mesh.
6. Calibrate extruder feed, then run a small central first-layer print with conservative motion and flow.
7. Expand the tested area gradually. Tune pressure advance, input shaping, acceleration and volumetric flow only after mechanical and thermal checks pass.

Follow [Klipper bed leveling](https://www.klipper3d.org/Bed_Level.html), [rotation distance](https://www.klipper3d.org/Rotation_Distance.html), and [resonance compensation](https://www.klipper3d.org/Resonance_Compensation.html) for the respective procedures.

**Release gate:** repeatable homing, verified travel, correct heater/sensor pairing, stable control, clean first layers and a recorded working configuration. Mark this guide validated only after the real build passes these checks.
