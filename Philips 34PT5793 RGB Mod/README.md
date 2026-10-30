> [!WARNING]  
> I am not an electrical engineer. I developed this mod using internet resources and examples, as well as trial and error. I am not responsible for any damage to your CRT or consoles, nor any injuries sustained.

Chassis:  A8.0A-AA  
Jungle: TDA8844  
Tube: Philips A80ECK272X95

Important boards:
- A7: RGB/Jungle
- E: External RGB I/O (Europe model only)

# RGB Mod

Unpopulated RGB input: M20 (page 48)

The circuit actually combines three sources of RGB: OSD, teletext, and external RGB. Factory external RGB installation requires several components including an RGB switch IC. This turned out to be more complicated than initially thought, with quite a few components in a tight space, as well as a few extra missing jumpers that are not indicated in the schematic. In hindsight, it might actually be simpler to takeover the teletext (TXT) RGB lines as they are already populated.

The OSD is visible but has a black smear/bleed. It is acceptable for my own use, and I'm not sure why it is like this or how address it.

Components to install:

| Part No | Type                   | Value         | Format               | Notes                            |
| ------- | ---------------------- | ------------- | -------------------- | -------------------------------- |
| 7275    | IC / RGB switch        | TDA8601       | DIP-16               | RGB/blanking switch              |
| 2275    | Ceramic capacitor      | 47 nF, 50 V   | SMD 0805             | OSD Red coupling                 |
| 2276    | Ceramic capacitor      | 47 nF, 50 V   | SMD 0805             | OSD Green coupling               |
| 2277    | Ceramic capacitor      | 47 nF, 50 V   | SMD 0805             | OSD Blue coupling                |
| 2278    | Ceramic capacitor      | 47 nF, 50 V   | SMD 0805             | External Red coupling            |
| 2279    | Ceramic capacitor      | 47 nF, 50 V   | SMD 0805             | External Green coupling          |
| 2280    | Ceramic capacitor      | 47 nF, 50 V   | SMD 0805             | External Blue coupling           |
| 2290    | Electrolytic capacitor | 100 µF, 25 V  | Radial               | +8 V feed to TDA8601             |
| 2291    | Ceramic capacitor      | 100 nF, ≥25 V | SMD 0805             | TDA8601 +8 V supply decoupling   |
| 3290    | Resistor               | 10 Ω, ~0.5 W  | TH Axial, Flameproof | +8 V feed to TDA8601             |
| 3280    | Resistor               | 1 kΩ          | SMD 0805             | External fast-blanking input     |
| 3281    | Resistor               | 4.7 kΩ        | SMD 0805             | TDA8601 SEL / OSD-priority       |
| 3282    | Resistor               | 4.7 kΩ        | SMD 0805             | TDA8601 SEL / OSD-priority       |
| 7282    | NPN transistor         | BC847B        | SOT-23               | Automatic OSD priority           |
| M20     | Connector              | 1×5 header    | 2.54mm               | Optional; R, G, B, FFBL_EXT, GND |
| 9287    | Jumper                 |               |                      | 8V supply line                   |
| 9276    | Jumper                 |               |                      | Blanking                         |
| 4275    | Jumper                 |               | SMD                  | SEL                              |
| 9292    | Jumper                 |               |                      | Sandcastle                       |

Components to remove:

| Part No | Type            | Value | Notes                                                                                                     |
| ------- | --------------- | ----- | --------------------------------------------------------------------------------------------------------- |
| 4276    | Jumper resistor | 0 Ω   | Non-SCART TDA8601 bypass                                                                                  |
| 4277    | Jumper resistor | 0 Ω   | Non-SCART TDA8601 bypass                                                                                  |
| 4278    | Jumper resistor | 0 Ω   | Non-SCART TDA8601 bypass                                                                                  |
| 4279    | Jumper resistor | 0 Ω   | Non-SCART TDA8601 bypass. Be careful not to mistake 3283 for this component, the silkscreen is confusing. |

Components to include on the RGB input side:

| Part No | Type     | Value | Notes                 |
| ------- | -------- | ----- | --------------------- |
| R-IN-R  | Resistor | 75 Ω  | Red termination       |
| R-SER-R | Resistor | 100 Ω | Red series resistor   |
| R-IN-G  | Resistor | 75 Ω  | Green termination     |
| R-SER-G | Resistor | 100 Ω | Green series resistor |
| R-IN-B  | Resistor | 75 Ω  | Blue termination      |
| R-SER-B | Resistor | 100 Ω | Blue series resistor  |
| GND     |          |       |                       |
```
DE-15 R ──┬── 75Ω ── GND
          └── 100Ω ── M20-1

DE-15 G ──┬── 75Ω ── GND
          └── 100Ω ── M20-2

DE-15 B ──┬── 75Ω ── GND
          └── 100Ω ── M20-3
          
DE-15 GND ─── GND
```

Blanking:

| Part No | Type     | Value  | Notes                                           |
| ------- | -------- | ------ | ----------------------------------------------- |
| BL-R1   | Resistor | 4.7 kΩ | Upper divider resistor from local +8 V supply   |
| BL-R2   | Resistor | 2.2 kΩ | Pull-down/divider resistor from FFBL_EXT to GND |
| BL-SW   | Switch   | SPST   | Optional; omit for permanently enabled blanking |

```
2290 positive / TDA8601 pin 1 (+8 V)
        │
       4.7k
        │
     SPST switch
        │
        ├──────────── M20 pin 4  (FFBL_EXT)
        │
       2.2k
        │
        └──────────── M20 pin 5  (GND)
```

Sync:

Connect to AV1 or AV2 video.
