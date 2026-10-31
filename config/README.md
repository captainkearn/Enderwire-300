# Configuration staging

This folder is reserved for the verified Enderwire 300 configuration. No runnable configuration is included in v0.1.

Before adding `printer.cfg`, record board revisions, drivers, motor mapping, hotend/sensor models, probe, homing strategy, travel limits and CAN topology in the build record. Include only files matching the actual built machine. See [commissioning](../docs/07-klipper.md).

Suggested future organization: `printer.cfg` for includes and machine limits; `mcu.cfg` for verified transport identities; `motion.cfg`; `toolhead.cfg`; `bed.cfg`; and `macros.cfg`. These filenames are suggestions, not files currently shipped.
