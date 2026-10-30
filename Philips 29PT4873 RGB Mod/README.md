> [!WARNING]  
> I am not an electrical engineer. I developed this mod using internet resources and examples, as well as trial and error. I am not responsible for any damage to your CRT or consoles, nor any injuries sustained.

Chassis: L9.1A-AA
Jungle: TDA8843
Micom: SAA5565
Tube: A68AJB82X01

## RGB Mod

> [!WARNING]  
> I compiled this list from the scrawlings from my notes after experimenting with this mod. It should not be treated as a complete and verified list.
> If you intend to attempt this mod, you should ideally have experience with RGB modding, and should be prepared to verify and troubleshoot the circuitry if needed.

| Part | Role                         | Before | After |
| ---- | ---------------------------- | ------ | ----- |
| 3231 | RGB Inline Resistor          | N/A    | 270R  |
| 3232 | RGB Inline Resistor          | N/A    | 270R  |
| 3233 | RGB Inline Resistor          | N/A    | 270R  |
| 6602 | OSD Blanking Inline Diode    | Jumper | Diode |
| 6603 | OSD Inline Resistor          | Jumper | 680R  |
| 6604 | OSD Inline Resistor          | Jumper | 680R  |
| 6605 | OSD Inline Resistor          | Jumper | 680R  |
| 9230 | OSD Inline Diode             | Jumper | Diode |
| 9231 | OSD Inline Diode             | Jumper | Diode |
| 9232 | OSD Inline Diode             | Jumper | Diode |

The following may be necessary, haven't tested without:

| 3671 | RGB Blanking Inline Resistor | N/A | 220R  |
| ---- | ---------------------------- | --- | ----- |
| 6608 | RGB Blanking Inline Diode    | N/A | Diode |
| 3686 | SCART Pin 8/S-Video Term Res | 8K2 | N/A   |

