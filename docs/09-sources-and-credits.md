# 9. Sources, attribution, and licensing

[Guide index](../README.md)

Sources reviewed October 31, 2026. Hardware specifications in this repository are identified as builder-confirmed, source-derived, or pending; descriptions of the actual Enderwire 300 build come from Captain Kearn.

## Design lineage

| Project / creator | Role | Primary source |
| --- | --- | --- |
| Trinity Nova Max Neo V1 / Jackmiller | Max Neo conversion model set and reference render | [Printables model 974893](https://www.printables.com/model/974893-trinity-nova-max-neo-v1-ender-3-max-neo-to-enderwi) |
| Ender_SW / boubounokefalos, also known as DaRk_dOg | Smaller Pro/V2 conversion reference used by the builder | [Repository](https://github.com/boubounokefalos/Ender_SW) |
| FT Enderwire / FizzysTech | Additional source explicitly linked by Trinity's PDF | [Repository and wiki](https://github.com/fizzystech/ft_enderwire) |
| FT EMS mounts / Fizzy | Mount lineage credited by Trinity | [Mounts repository](https://www.printables.com/model/558357-ft-ems-mounts-repository) and [SWC V2](https://www.printables.com/model/588776-ft-ems-swc-v2) |
| Triano | Earlier conversion credited by Ender_SW | [Original conversion](https://github.com/walttriano/VoronUsers/tree/master/printer_mods/Triano/Ender_3Pro_Switchwire) |
| Voron Design | Switchwire platform and assembly reference | [Voron-Switchwire](https://github.com/VoronDesign/Voron-Switchwire) |
| Dragon Burner / chirpy2605 | Toolhead documentation, component selection and adapters | [Dragon Burner](https://github.com/chirpy2605/voron/tree/main/V0/Dragon_Burner) |
| MapleLeafMakers | Dragon Burner configurator credited upstream | Access through the Dragon Burner documentation |
| Mellow | Hardware manufacturer and authoritative board references | [C5 docs](https://mellow.klipper.cn/en/docs/category/fly-c5/) |
| Klipper contributors | Firmware configuration and verification procedures | [Klipper documentation](https://www.klipper3d.org/) |

The Printables web page could not be fetched during preparation. The supplied 15-page PDF was inspected instead. It identifies Jackmiller, a publication/update date of August 28, 2025, the model list, FizzysTech/Ender_SW/Voron links, and a CC BY-SA 4.0 license link. The PDF is not republished in this package. All 98 supplied Trinity STL files are included unmodified under [STLs/Trinity](../STLs/Trinity/README.md); the STL inventory records their original paths and SHA-256 hashes.

## Included images

| Local file | Creator and source | License / treatment |
| --- | --- | --- |
| `images/reference/trinity-nova-max-neo.png` | Jackmiller; first embedded image in the supplied Trinity Printables PDF | CC BY-SA 4.0 as stated by the PDF; extracted without visual edits |
| `images/reference/ender-sw-reference-front.png` | boubounokefalos / DaRk_dOg; Ender_SW `1.png` | Unmodified; upstream repository GPL-3.0; license copy included |
| `images/reference/ender-sw-reference-enclosed.png` | boubounokefalos / DaRk_dOg; Ender_SW `2.png` | Unmodified; upstream repository GPL-3.0; license copy included |

The two Ender_SW files were fetched from the repository. The reference baseline is commit `f5556ba3f83db3e15cfd411859f369d85cbd6634`; image 2 and the license were fetched at that commit. Image 1 was fetched from `main` during the same research session. The downloaded asset hashes are in [the image manifest](../bom/image-manifest.csv).

- [Ender_SW 1.png](https://github.com/boubounokefalos/Ender_SW/blob/f5556ba3f83db3e15cfd411859f369d85cbd6634/1.png)
- [Ender_SW 2.png](https://github.com/boubounokefalos/Ender_SW/blob/f5556ba3f83db3e15cfd411859f369d85cbd6634/2.png)
- [Ender_SW license](../third_party/Ender_SW-LICENSE.txt)
- [CC BY-SA 4.0 terms](https://creativecommons.org/licenses/by-sa/4.0/)

These are upstream reference renders, not stock photography of this build. Their depicted toolheads, proportions and electronics must not be represented as the finished Enderwire 300. No manufacturer photographs or custom wiring diagrams have been included without establishing their relevance and provenance.

## Publication boundaries

See [NOTICE.md](../NOTICE.md). This package adds original draft prose, inventory metadata and project organization. Existing assets retain their own licenses. No blanket repository license has been selected for the new material on the builder's behalf. Before adding modified upstream CAD/STLs, retain required notices and document the source, changes and applicable license for each imported set. The existing licenses are not replaced by this notice.
