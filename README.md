# Automated Product Mixers

Designed and implemented an automated control system for product mixers to upgrade on existing ones. Incorporated new safety features including safety relays to maximize operators' safety. Automated the mixing process to enhance efficiency.

**Live site:** [https://jkabui.github.io/Automated-Product-Mixers/](https://jkabui.github.io/Automated-Product-Mixers/)

## System Description

This project implements an automated control system for an industrial product mixer (agitator) using a Siemens S7-1200 PLC programmed in TIA Portal V19. The electrical schematics were designed using EPLAN Electric P8.

**Safety Circuit**  
A dual-channel safety relay monitors:
- Dual-channel Emergency Stop button  
- Dual-channel safety limit switch on the access door  
- Dual-channel safety limit switch on the top cover  

The safety relay only energizes the `SAFETY_OK` signal when the Emergency Stop is released **and** both the door and top cover are fully closed. This signal is fed as a hardwired input to the PLC. In addition, the motor overload relay status is monitored by the PLC.

**Motor Control Logic**  
The agitator motor is controlled through two contactors (Forward and Reverse) and a thermal overload relay.  

When the Start button is pressed (and all safety conditions are healthy):
1. The motor runs in the **forward** direction for 30 seconds  
2. Stops for 3 seconds  
3. Runs in the **reverse** direction for 30 seconds  
4. Stops for 3 seconds  

This forward–pause–reverse–pause cycle repeats continuously until the Stop button is pressed or any safety condition is lost (`SAFETY_OK` drops or the overload relay trips).

## Project Files

### PDF Documents
- [📄 Powder Products Mixer (PDF)](./Powder%20Products%20Mixer.pdf)
- [📄 PLC Program (PDF)](./PLC_Program.pdf)

### Circuit Drawings (.dxf)
- [1. Power Circuit.dxf](./1.Power%20Circuit.dxf)
- [2. Safety Circuit.dxf](./2.Safety%20Circuit.dxf)
- [3. PLC Circuit.dxf](./3.PLC%20Circuit.dxf)

### PLC Program (TIA Portal V19)
- [⬇️ Full TIA Portal Project (ZIP)](./Automatic%20Products%20Mixers.zip)

> **Note:**  
> - Download the ZIP file and open it with **TIA Portal V19** (or a compatible version).  
> - `.dxf` files can be opened with AutoCAD, DraftSight, or free DXF viewers.
