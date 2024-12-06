# DISCLAIMER  

I am not an electrical engineer. I developed this mod using internet resources and examples, as well as trial and error. I am not responsible for any damage to your CRT or consoles, nor any injuries sustained.

# LG CA-14A86 RGB Mux Mod

This chassis supports either a composite video input/output, or SCART RGB. From the factory, this set comes with the composite option. We can uninstall the composite input block and replace it with a SCART socket. While the Jungle chip has RGB inputs, the existing OSD to Jungle circuit is abnormal so using the established RGB mux mod approach may not work.   
  
However, since the chassis has support for combining external RGB input as well as teletext input (also unpopulated) with the OSD RGB signals, we can install a partial implementation of these components for our mod to work.  

## Infomation and Resources

Jungle: TDA8362B
Chassis: MC-64A

[Service Manual](./res/service_manual.png)

## Component Value Changes

| Part #       | Component    | Value      |
| ------------ | ------------ | ---------- |
| A000         | SCART Socket |            |
| A000         | Jump         |            |
| A000         | Resistor     | 00 Ohm     |

### Additional Steps  
