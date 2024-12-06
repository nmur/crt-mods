> [!WARNING]  
> I am not an electrical engineer. I developed this mod using internet resources and examples, as well as trial and error. I am not responsible for any damage to your CRT or consoles, nor any injuries sustained.

# LG CA-14A86 RGB Mux Mod

This chassis supports either a composite video input/output, or SCART RGB. From the factory, this set comes with the composite option. We can uninstall the composite input block and replace it with a SCART socket. While the Jungle chip has RGB inputs, the existing OSD to Jungle circuit is abnormal so using the established RGB mux mod approach may not work.   
  
However, since the chassis has support for combining external RGB input as well as teletext input (also unpopulated) with the OSD RGB signals, we can install a partial implementation of these components for our mod to work.  

## Infomation and Resources

Jungle: TDA8362B  
Chassis: MC-64A

[Service Manual](./res/service_manual.png)

## Component Value Changes

| Part #       | Component    | Value       |
| ------------ | ------------ | ----------- |
| PJ201        | SCART Socket | Right Angle |
| R206         | Resistor     | 75 Ohm      |
| R207         | Resistor     | 75 Ohm      |
| R208         | Resistor     | 75 Ohm      |
| R222         | Resistor     | 75 Ohm      |
| J61          | Jump         |             |
| J77          | Jump         |             |
| J78          | Jump         |             |
| C204         | Electrolytic Capacitor | 10uF 16V           |
| C205         | Electrolytic Capacitor | 10uF 16V           |
| C206         | Electrolytic Capacitor | 10uF 16V           |
| R213         | Resistor     | 100 Ohm     |
| R214         | Resistor     | 100 Ohm     |
| R215         | Resistor     | 100 Ohm     |
| D506         | Jump         |             |
| D506         | Jump         |             |
| D506         | Jump         |             |
| D503         | Diode        | 1N4148      | 
| D504         | Diode        | 1N4148      |
| D505         | Diode        | 1N4148      |
| J73          | Jump         |             |
| R65          | Resistor     | 100 Ohm     |
| R66          | Resistor     | 100 Ohm     |
| R67          | Resistor     | 100 Ohm     |
| R68          | Resistor     | 100 Ohm     |

### Additional Steps  

For the unpopulated IC202, bridge the following pins:  
- 1 <-> 16  
- 4 <-> 13  
- 6 <-> 11  
- 8 <-> 9  
