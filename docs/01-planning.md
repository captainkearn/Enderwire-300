# 1. Planning and donor preparation

[Guide index](../README.md) | [Next: Parts](02-parts.md)

## Establish your build variant

Start with the [build record](11-build-record.md). Record the mainboard revision, driver models, toolhead board revision, hotend SKU, extruder, probe, and homing method. Take readable photographs of product labels. A board name alone does not establish its pinout, jumper settings, or firmware target.

Enderwire 300 reuses the Max Neo frame and stock Ender motors. Reusing the bed, power supply, display, and stock switches is subject to inspection and compatibility checks. Do not assume that the original extruder motor fits the chosen direct-drive extruder.

## Tools

| Tool | Use |
| --- | --- |
| Metric hex keys and suitable spanners | Frame and printed assemblies |
| Calipers, ruler/tape, square | Hardware, rail layout, frame alignment |
| Multimeter | Continuity, polarity and de-energized CAN checks |
| Correct crimp tools and connector terminals | Reliable replacement harnesses |
| Controlled-temperature insert tool | Heat-set inserts where specified by the model |
| Flush cutters, deburring tools, labels | Finishing and harness organization |
| Soft gantry supports and rail stops | Prevent gantry drops and carriage loss |

## Before disassembly

1. Save the current firmware configuration and slicer profile. Label them as donor backups, not conversion defaults.
2. Photograph the full printer, underside, bed wiring, motor labels, endstops, and power supply label.
3. Unplug mains and other sources of power, including USB. Follow the supply manufacturer's discharge precautions; do not open the PSU.
4. Label both ends of every cable before disconnecting it. Keep mains, bed heater, bed sensor, motor and fan wiring distinguishable.
5. Support the X gantry before removing lead screws, couplers, belts, or motor mounts.
6. Bag fasteners by assembly. Inspect the frame, motor cables, bed strain relief and connectors for damage.

## Strip only what the conversion replaces

Remove the donor toolhead, Bowden path, electronics mounts, wheel carriages and lead-screw hardware as required by the chosen conversion parts. Keep the donor's reusable hardware until the finished build has passed testing. Do not cut the X extrusion using an Ender_SW dimension: establish the Max Neo assembly width first.

## Measure before ordering or cutting

Record frame width, upright spacing, X extrusion length and section, usable rail mounting surfaces, bed hole spacing and bed cable exit. Record each rail's overall length, carriage type and usable stroke separately. A longer rail is not automatically compatible with a printed mount or a fixed bed carrier.

**Gate:** donor photographed, components labeled, frame condition checked, gantry supported, parts variants selected. Continue when these are complete.

**Photo to add:** `P01` donor overview and `P02` bare frame, from the [photo checklist](10-photos.md).
