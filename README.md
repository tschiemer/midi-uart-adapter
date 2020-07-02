# midi-uart-adapter

PCB layout for a simple MIDI (In-Through-Out) / UART - Adapter according to MIDI 1.0 Specification

Does not directly include footprints for MIDI or TRS plugs but rather provides headers such as to more easily allow customization.

Also allows to use different voltage levels for RX, TX respectively (please use different resistors according to recommendations).

https://github.com/tschiemer/midi-uart-adapter

According to simple table-top tests using a Behringer BCF2000 all three connections (in, through, out) work as expected.

![PCB](https://github.com/tschiemer/midi-uart-adapter/blob/master/README-PCB.png?raw=true)

## Parts

- [LITEON 6N138](https://datasheet.octopart.com/6N139-Lite-On-datasheet-8327661.pdf) or [ONSEMI 6N138](https://www.onsemi.com/pub/Collateral/HCPL2731-D.PDF) Octocoupler
- [ONSEMI 1N914](https://www.onsemi.com/pub/Collateral/1N914-D.PDF) Laser Diode
- Resistors (RA, RB, RC, RD, RE, RF) when Vrx = Vtx = 5V: 220 Ohm 5% 0.25W, Package 1206 (3216 Metric) (ex. [ Bourns Inc. CR1206-FX-2200ELF](https://www.bourns.com/docs/product-datasheets/CRxxxxx.pdf) )
- *Optional* Ferrite Beads (FB1-6), 1kOhm @ 1MHz, Package 0603 (1608 Metric) (ex. [TDK Corporation MMZ1608Y102BTA00](https://product.tdk.com/en/search/emc/emc/beads/info/print_pdf)), bridge if not used
- *Optional* ~~Capacitor (C1), 0.1UF, Package 0201 (0603 Metric) (ex. [Murata Electronics GRM033C80J104KE15D](https://search.murata.co.jp/Ceramy/image/img/A01X/G101/ENG/GRM033C80J104KE15-01A.pdf)), leave unconnected if not used (works, but too *tiny* package size to solder by hand; well, it's possible ;) )~~
- *Optional* Capacitor (C1), 0.1UF, Package 0603 (1608 Metric) (ex. [KEMET C0603C104K4RACTU](https://www.digikey.com/product-detail/en/kemet/C0603C104K4RACTU/399-1096-1-ND/411371)), leave unconnected if not used

The optional parts (ferrite beads and capacitor) are intended to surpress EMI etc.

## Connections

### H1 (Header 1)

| Pin | Description |
|---|---|
| Vrx | Receiver voltage (standard: +5V) |
| Vtx | Transmitter voltage (standard: +5V) |
| G | Ground |
| Rx | UART RX* |
| Tx | UART TX* |

*According to standard: 31.25 (+/- 1%) Kbaud, asynchronous, with a start bit, 8 data bits (D0 to D7), and a stop bit

*Note* if you are using different voltages than 5V (ie 3.3V) you need other resistor values. Also see electrical specs for suggestion.

### Midi-In/-Through/-Out

| DIN-5pole 180deg Pin* | TRS Connector |
|---|---|
| 2 | T |
| 4 | R |
| 5 | S |

*Pins 1 and 3 are not connected.


## Changelog

v2.1
- Reduced size to fit into 4x5cm
- Added license on silkscreen

v2.0
- Removed unnecessary header pins
- More compact / smaller board size


## References

- [MIDI Electrical Specification Update [2014]](https://www.midi.org/downloads?task=callelement&format=raw&item_id=100&element=f85c494b-2b32-4109-b8c1-083cca2b7db6&method=download)
- [Specification for Use of "TRS" Connectors with MIDI Devices](https://www.midi.org/downloads?task=callelement&format=raw&item_id=171&element=f85c494b-2b32-4109-b8c1-083cca2b7db6&method=download)
