# 4. CoreXZ gantry, belts, and counterbalance

[Previous](03-frame-and-y.md) | [Guide index](../README.md) | [Next](05-toolhead.md)

CoreXZ couples two motors to X and Z motion. The motor connected as `stepper_x` does not behave like a Cartesian X motor in isolation. The original lead-screw Z configuration must not be reused for belt-driven CoreXZ.

## Install vertical guides and gantry

1. Secure a support under the gantry before assembling the belt drive.
2. Align the vertical rails with a consistent datum. Check their parallelism at top, middle and bottom.
3. Assemble the selected left/right XZ block halves with their intended spacers and fasteners. Keep carriage screws accessible.
4. Fit the X extrusion at the length established for the Max Neo assembly. Do not use the Pro/V2 cut length.
5. Install the X rail and selected toolhead carriage. Verify that its attachment and belt clamps match the intended Dragon Burner adapter.
6. Check free X movement and move the supported gantry vertically. Resolve racking or friction before installing the drive belts.

## Motors, upper blocks and idlers

Use the selected Trinity Z motor mounts and upper blocks only after checking their hardware stack in CAD. Record pulley tooth counts, belt pitch/width, shaft bores, bearing orientation and spacer placement. Retained donor motors may need compatible replacement pulleys; do not hammer pulleys onto shafts or force off press-fit pulleys in a way that damages bearings.

Fit pulley grub screws against the shaft flat where applicable. Confirm adequate shaft engagement and clearance from the mount. Check that the fastener clamp load acts through the intended spacers and bearing races without preventing idler rotation.

## Route the CoreXZ belts

**Routing verification required:** the supplied model inventory does not establish a complete, illustrated Enderwire 300 belt route. Use the matching selected CAD and the [official Switchwire assembly reference](https://github.com/VoronDesign/Voron-Switchwire), then document the physical route before releasing this section as a reproducible recipe. The general checks below do not replace that route.

1. Identify the two independent belt loops and every pulley/idler/contact surface in the selected assembly.
2. Thread each loop with the gantry supported. Match the intended toothed/backside contact at each turn.
3. Check belt planes from above and from the side. Belts must not rub flanges, printed blocks, fasteners, wiring or each other.
4. Secure the ends using the matching clamps. Keep tensioners within their adjustment range and leave service tails.
5. Apply moderate, balanced tension. Move the mechanism slowly through its envelope and recheck alignment before trimming tails.

Do not publish a generic tension frequency as an Enderwire 300 target without specifying the measured free span and belt specification.

## Counterbalance

The Trinity archive includes Key-Bak and door-puller mount options. Choose a single compatible arrangement and verify its reach, attachment points and retraction force for the actual Dragon Burner gantry mass. Do not install every alternative mount merely because it is in the archive.

With a support still close below the gantry, check top and bottom positions for cable reach and hard stops. Keep hands clear of the drop path. Do not assume the counterbalance makes motor disable safe until its behavior has been verified.

**Gate:** supported full-range motion is smooth, belts track consistently, gantry remains square, counterbalance stays within its working range, and photos show both complete belt routes.

**Photos to add:** `P06` both complete CoreXZ belt routes, `P07` lower motors and upper idler stacks, `P08` counterbalance at both extremes. These close-ups are necessary before others can reproduce the belt installation confidently.
