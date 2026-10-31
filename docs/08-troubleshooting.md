# 8. Troubleshooting and maintenance

[Previous](07-klipper.md) | [Guide index](../README.md) | [Next: Sources](09-sources-and-credits.md)

| Symptom | First checks | Completion evidence |
| --- | --- | --- |
| Bed reads an impossible negative temperature / ADC out of range | Power down; trace sensor to the actual MCU and connector; inspect open circuits, pin assignment and sensor type | Stable plausible ambient temperature on the correct channel |
| Toolhead temperature is missing or implausible | Exact sensor SKU, compatible interface, toolhead MCU prefix, connector and pull-up arrangement | Correct sensor responds to gentle warming |
| Motor buzz works but homing fails | Homing method, switch behavior or DIAG mapping, driver setup and motion direction | Individual axis homes correctly under supervision |
| Physical endstop always triggered | Connector pinout, switch continuity, pull-up and inversion | Released and actuated states change correctly |
| Sensorless state appears triggered at rest | Driver-specific behavior, DIAG pin/jumper and TMC configuration | Correct controlled homing behavior, not just a static query |
| X command produces unexpected Z motion | CoreXZ config, two motor directions, driver mapping and belt routing | Coordinated axis motion agrees with commands |
| Gantry falls when motors disable | Support gantry; check counterbalance, belt clamps and tension | Controlled supported check confirms intended behavior |
| Bed or gantry binds | Rail parallelism, distorted mounts, screw protrusion and carrier alignment | Smooth travel throughout the envelope |
| Belt walks/rubs | Pulley/idler planes, spacer stack, clamp location and belt twist | Belt remains centered through full motion |
| CAN disconnects during motion | Strain relief, crimps, termination, bitrate, topology and power drop | Stable communication while exercising the envelope |
| Heater rises while commanded off | Remove power immediately; inspect output wiring and failed switching hardware | Fault resolved and supervised channel checks repeated |
| Duct touches print / travel is reduced | Nozzle projection, toolhead adapter, probe and actual limits | Re-measured travel and collision-free motion |

Do not bypass thermal protections, increase allowed error thresholds, or raise motor current to hide an unresolved mechanical/wiring fault.

## Maintenance record

Before use, inspect harness strain relief, bed leads, loose fasteners, belt condition, fan operation and temperature plausibility. Follow the rail supplier's lubrication schedule. After transport or changing toolhead components, recheck squareness, clearance, homing and Z reference. Review electrical terminals periodically with all power disconnected.

Log the date, symptom, observations, actual change and verification result. Change one relevant variable at a time and keep the previous working configuration available.
