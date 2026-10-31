# 2. Bill of materials and printed parts

[Previous](01-planning.md) | [Guide index](../README.md) | [Next](03-frame-and-y.md)

This is a procurement worksheet. Quantities and dimensions marked **measure** must be established from the selected CAD and physical printer before purchasing. No complete, verified Enderwire 300 shopping BOM has been established yet.

## Hardware worksheet

| Group | Item | Quantity | Selection notes |
| --- | --- | --- | --- |
| Donor | Ender 3 Max Neo frame | 1 | Inspect and square |
| Motion | Original Ender motors | Map each installed motor | Record label, shaft, pulley and driver assignment |
| Bed | Donor bed/carrier/heater | Inspect for reuse | Match Trinity carrier holes and cable clearance |
| Guides | Linear rails with carriages | Measure selected layout | Trinity filenames reference MGN12H; verify every interface and length |
| Drive | Belts and drive pulleys | Measure | Match pitch, width, tooth count, bore, and belt path |
| Drive | Idlers, bearings, shafts, spacers | CAD dependent | Do not substitute toothed/smooth contact surfaces blindly |
| Frame | Additional/reworked extrusions | Measure | Record actual cut list; do not use Pro/V2 dimensions |
| Hardware | Screws, nuts, T-nuts, washers, inserts | CAD dependent | Record each joint and screw engagement |
| Counterbalance | Key-Bak or selected alternative | Variant dependent | Match gantry mass, reach and attachment layout |
| Control | Mellow FLY-C5 | 1 | Record PCB revision and driver type |
| Control | Mellow toolhead board | 1 | Exact model/revision pending |
| Toolhead | Dragon Burner printed assembly | 1 selected set | Select compatible carriage, extruder and hotend mounts |
| Toolhead | ALPS Ultra HF hotend | 1 | Exact hotend/heater/sensor identification pending |
| Toolhead | Extruder assembly and motor | 1 compatible set | Do not assume donor motor compatibility |
| Cooling | Toolhead fans | Selected variant | Upstream v8 baseline uses two 4010 blowers and a 3010 heatsink fan; verify installed variant |
| Detection | Endstops / probe | Chosen strategy | Mechanical, sensorless and probing are separate decisions |
| Power | PSU, input protection, earth, distribution | Rated for loads | Reuse only after inspection and load calculation |
| Harness | Motion-rated wires, connectors, strain relief | Measure | Verify fan voltages and board connector pin order |
| CAN | Twisted data pair, termination, interface | If used | Topology and host/interface arrangement to confirm |

## Trinity model selection

The supplied archive contains these groups. The CSV inventories every STL with its original relative path and SHA-256. Filename suffixes such as `x2` are hints from the source; they are not verified assembly quantities.

| Source folder | Likely role | Enderwire 300 selection |
| --- | --- | --- |
| X Gantry | Left/right XZ blocks | Candidate; dry-fit to selected rails and beam |
| Y Gantry | Carrier, motor mount, idler, endstop, chains | Candidate; verify bed and rail geometry |
| Z Gantry | Motors, tensioners, upper blocks, stops | Candidate; verify belt hardware and travel |
| Keybak-Door Puller Mount | Counterbalance mounting options | Select one compatible mechanism |
| Extrusion Expand Front / Rear | Frame extensions | Check fit and cable/input clearance |
| EMS | Electronics mounting structure | C5 mount may need a separate compatible adapter |
| Deckpanel Splitted | Deck and cable covers | Fit after motion and wiring checks |
| Front Skirt / Rear Skirts | Display, inlet, fan covers | Includes source-specific display/fan choices; select deliberately |
| Feeds | Source-named base/foot components | Confirm geometry and orientation before use |
| Misc Parts | Fan and distribution mounts | Match actual components |
| Tools | MGN12 alignment guide | Assembly aid if compatible |
| Stealthburner Assembly | Source toolhead and related carriage parts | Do not print the full set for Dragon Burner; assess shared carriage/belt-clamp needs separately |

The source numbering is retained, including gaps. It does not imply a build order. Some files are alternatives rather than cumulative requirements.

## Printing and fit checks

Use the material and print guidance from the specific upstream component. For structural parts exposed to enclosure heat, use an appropriate heat-resistant material; do not treat PLA as a universal structural substitute. Print at the model's intended scale. Verify hole fits and insert dimensions using a small representative part before committing to the full set.

1. Choose the exact variant and keep its filename/source in the build record.
2. Check orientation and load direction in CAD. Do not rely on a filename for orientation.
3. Inspect layer adhesion, holes and belt channels. Reject cracked or warped structural parts.
4. Install only the insert type specified by the part geometry; keep inserts square.
5. Trial-fit fasteners without forcing them. Check that screws do not bottom out, touch rails, or protrude into belts.

**Gate:** all structural parts and mating hardware dry-fit, rail lengths and pulley geometry established, and a selected BOM recorded.
