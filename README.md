# midi-uart-adapter

PCB layout for a simple MIDI (In-Through-Out) / UART - Adapter according to MIDI 1.0 Specification

*** NOT YET TESTED ***

Does not directly include footprints for MIDI or TRS plugs but rather provides headers such as to more easily allow customization.

Also allows to use different voltage levels for RX, TX respectively (please use different resistors according to recommendations).

https://github.com/tschiemer/midi-uart-adapter

***Please note, this is my first PCB design ever which at this very moment has not been tested yet - hopefully soon to come.***

![PCB v1.0~alpha](https://github.com/tschiemer/midi-uart-adapter/blob/master/README-PCB.png?raw=true)

## Parts

- [LITEON 6N138](https://datasheet.octopart.com/6N139-Lite-On-datasheet-8327661.pdf) or [ONSEMI 6N138](https://www.onsemi.com/pub/Collateral/HCPL2731-D.PDF) Octocoupler
- [ONSEMI 1N914](https://www.onsemi.com/pub/Collateral/1N914-D.PDF) Laser Diode
- Resistors (RA, RB, RC, RD, RE, RF) when Vrx = Vtx = 5V: 220 Ohm 5% 0.25W, Package 1206 (3216 Metric) (ex. [ Bourns Inc. CR1206-FX-2200ELF](https://www.bourns.com/docs/product-datasheets/CRxxxxx.pdf) )
- *Optional* Ferrite Beads (F1-6), 1kOhm @ 1MHz, Package 0603 (1608 Metric) (ex. [TDK Corporation MMZ1608Y102BTA00](https://product.tdk.com/en/search/emc/emc/beads/info/print_pdf)), bridge if not used
- *Optional* Capacitor (C1), 0.1UF, Package 0201 (0603 Metric) (ex. [Murata Electronics GRM033C80J104KE15D](https://search.murata.co.jp/Ceramy/image/img/A01X/G101/ENG/GRM033C80J104KE15-01A.pdf)), leave unconnected if not used

The optional parts (ferrite beads and capacitor) are intended to surpress EMI etc.

## Changelog

v2.0
- Removed unnecessary header pins
- More compact / smaller board size


## References

- [MIDI Electrical Specification Update [2014]](https://www.midi.org/downloads?task=callelement&format=raw&item_id=100&element=f85c494b-2b32-4109-b8c1-083cca2b7db6&method=download)
- [Specification for Use of "TRS" Connectors with MIDI Devices](https://www.midi.org/downloads?task=callelement&format=raw&item_id=171&element=f85c494b-2b32-4109-b8c1-083cca2b7db6&method=download)
