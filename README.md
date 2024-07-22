# Forge, Hack Club's 3D Printer

## WIP Disclaimers

* This is an upcoming [Hack Club](https://hackclub.com) You Ship, We Ship (YSWS) program.
* Things are still under heavy development as the Forge Editor and the Forge Printer are WIP (Work in Progress) projects
* All information on this README is subject to change at any moment
* Submission requirements, images, and links are not final. Websites URLs are placeholders and may not be functional
* If you have any questions about the Development of Forge (and are a teen under 18), feel free to visit #forge-dev on the [Hack Club Slack!](https://hackclub.com/arcade/?param=slack)

**[Landing Page](https://forge.hackclub.com)** | **[Forge Editor](https://forge.hackclub.com/editor)** | **[Gallery](https://forge.hackclub.com/gallery)**

Find problems in the world and use programatic 3D modeling to solve them. Submit your solutions to the Gallery and get a Forge 3D Printer
Blot is a **You Ship, We Ship** project from [Hack Club](https://hackclub.com).

> Forge is **fully open source**. The online editor can be freely used (or modified) by anyone, and we encourage all to submit to the gallery through PRs! However, you must be a teenager or younger to receive a free printer.

![image](https://github.com/Patcybermind/Project-Moonlight/assets/97562509/da8007c4-607d-4d73-ad87-6afdcd655585)

Building a model in the Forge editor is easy to learn, hard to master. You need abosultely no CAD or programming knowledge to get started. Since the Forge Editor is based on the [OpenSCAD](https://openscad.org) modeling language, it presents a challenge to even the most experienced parametric modelers.

## What is Forge exactly?

The Forge YSWS Project can be considered 2 major sections:

* Forge Printer - the fixed-bed cantilevered 3D Printer
* Forge Editor - the OpenSCAD-based online modeling software and slicer designed for the Forge Printer
  * Note that exporting to STLs is an option if you want to test your model on another 3D printer before you submit an PR.  

## About the Forge Printer

The printer is built after the [Flatpack](https://github.com/eponra/flatpack). However, this printer is signififcantly different internally than the Flatpack. Featuring a STM32 H5 series MCU and TMC2209 drivers on a custom Hack Club-engineered control board. The printer is designed to fit inside a filament box when folded, only taking up 220x210x75mm (not including the power supply or spool holder). Forge is the ultimate tool for competitions, club fairs, or hackathons.

## Specifications

**These are Forge's specification as of July 16, 2024. As we begin test manufacturing Forge, these specifications may change.**

* STM32H563VITX 32-Bit MCU
* TMC2209 Stepper Drivers
  * Reduced Motor Noise
  * Sensorless XY homing  
* TZ-E3 Hotend
  * 300°C Maximum Temperature
  * Designed around the Bambu Lab X1C hotend
  * 33mm³/s max flow rate
* 120x114x110 Heated Build Plate
  * Up to 100°C Print Temperature
  * Magnetic Textured PEI Plate
  * A small portion of print area is occupied by the Klicky Probe system
* MGN9C Linear Rails on all axes
* OLED and Rotary Encoder interface
* Sherpa Mini Direct Drive Extruder (DDE)
* Klicky Probe
  * Fully Automatic Bed Leveling (ABL)
  * Z offset is currently manual
* PLA, PETG, TPU capable
  * ABS and ASA are posssible but require ventilation and an enclosure
* Aluminum and 3D Printed ASA frame
* 250mm/s Tested Print Velocity
  * This number is an estimate, real print speeds will be updated as Forge's development continues

## Firmware

Forge will run on custom, open source Forge Firmware

* Forge is **not supported by Klipper**
  * Using forge with Klipper will require **replacing the mainboard** with an BigTreeTech SKR Pico and a Raspberry Pi Zero 2W alongside a seperately printed bracket (files will be provided at launch). Additionaly, no Klipper configuration files will be provided at this point. The bracket will still allow the printer to fold properly.

## Additional notes

* The BOM is at the bottom of this doc, and available as a CSV in `Electronics/Motherboard/billofmaterials.csv` for a more detailed view.
* The estimated value of the Forge Printer is $190-$250, but this estimate will change over time.
  * However, Forge will be **100% Free for teens 18 and under after designing 5 models and submiting a PR**
* Currently, Forge's parts and components are planned to be manufactured by [Siboor](https://www.siboor.com), a well established supplier of 3D Printing components.
* Forge is designed in Onshape. [Check out the 3D model!](https://cad.onshape.com/documents/490fa34c5c188f9b01dad5d1/w/4ce61de39bd6c276033d903d/e/7a262062418efbefd9181a13?renderMode=0&uiState=6696ce6038c5ba5455f5be75)

## How do I get a Forge Printer?

### 1) Find a problem

Look around! Find problems that 3D printing can fix. From a carabiner to a phone case!  

### 2) Design a solution

Using the Forge Editor, follow the turorials (link coming soon!) and program your solutions in OpenSCAD.  

### 3) Submit your design

The submission rules to get a Forge Printer for a PR are (not available, the Forge design guidelines will be accessable at launch). **You must be a teenager (or younger to qualify for a free machine)** but anyone can make a model and make a PR. Currently, we are requiring 5 Blot-level (of quality) models. This may change as the project progresses. While the full guidelines are not accessable, here's the basics of what you should(n't) do with your Forge project:

#### Dos and Don'ts

* A PR should have a .scad and .stl file
* Don't copy OpenSCAD code from other websites/generate code with AI (ChatGPT)
  * Doing so is considered plagirism. Anyone submitting fradulent code will be ineligible for a Forge Printer and may result in a violation of the Hack Club Code of Conduct
* Don't build your model in Parametric CAD software (Fusion, OnShape, Shapr3D, ect)
* Your model should be both functional and have some asthetic quality.
  * TL:DR, make it look nice
* Your model should have effort (roughly 8 hours per model)

### 4) Receive the parts to build your own Forge Printer

The bill of materials can be found here and isavailable as a CSV in `Electronics/Motherboard/billofmaterials.csv` and an assembly guide here (coming soon!).
Also note that, currently, the BOM is not polished as we communicate with Siboor.

| Reference                                 | Value                   | Datasheet                                                | Footprint                                              | Qty | DNP |
| ----------------------------------------- | ----------------------- | -------------------------------------------------------- | ------------------------------------------------------ | --- | --- |
| ABL1,FAN1,FAN2,FAN3,THM1,THM2,THM3,Z_END1 | B2B-XH-A                |                                                          | B2B-XH-A:JST_B2B-XH-A                                  | 8   |     |
| BED1,HOTEND1                              | 1751248                 |                                                          | Phoenix 1751248:PHOENIX_1751248                        | 2   |     |
| C1,C2,C3,C4                               | A750MV477M1VAAE018      | A750MV477M1VAAE018                                       | footprints:CAP_A750MV477M1VAAE018_KEM                  | 4   |     |
| C5,C6,C7                                  | GCM155R71H104KE02J      |                                                          | GCM155R71H104KE02J:CAPC1005X55N                        | 3   |     |
| DEBUG1                                    | Conn_01x04_Pin          | ~                                                        | PinHeader:PinHeader_1x04_P2.54mm_Vertical              | 1   |     |
| J1                                        | DX07S024JJ3R1300        |                                                          | DX07S024JJ3R1300:JAE_DX07S024JJ3R1300                  | 1   |     |
| M1,M2,M3                                  | AO3400A                 |                                                          | AO3400A:SOT95P280X125-3N                               | 3   |     |
| MCU1                                      | STM32H563VITx           | [https://www.st.com/resource/en/datasheet/stm32h563vi.pdf](https://www.st.com/resource/en/datasheet/stm32h563vi.pdf) | Package_QFP:LQFP-100_14x14mm_P0.5mm                    | 1   |     |
| MOTOR_E1,MOTOR_X1,MOTOR_Y1,MOTOR_Z1       | B4B-XH-A                |                                                          | B4B-XH-A:JST_B4B-XH-A                                  | 4   |     |
| PWR1                                      | PJ-102B                 |                                                          | PJ-102B:CUI_PJ-102B                                    | 1   |     |
| Q1,Q2                                     | IRFH7440TRPBF           |                                                          | IRFH7440TRPBF:TRANS_FDMS86202                          | 2   |     |
| R1,R2,R3,R4,R5,R6                         | RC1206JR-134K7L         |                                                          | RC1206JR-134K7L:RESC3216X65                            | 6   |     |
| R7                                        | RC0603FR-131KL          |                                                          | RC0603FR-131KL:0603                                    | 1   |     |
| R8,R9                                     | RMCF0805JT5K10          | ~                                                        | RMCF0805JT5K10:RESC2012X65N                            | 2   |     |
| REN1                                      | PEC11H-4015F-S0016      | PEC11H-4015F-S0016                                       | PinHeader:PinHeader_1x04_P2.54mm_Vertical              | 1   |     |
| SCRN1                                     | SSD1306                 |                                                          | PinHeader:PinHeader_1x04_P2.54mm_Vertical              | 1   |     |
| U1                                        | LM2576S-3.3_NOPB        |                                                          | LM2576S-3.3_NOPB:VREG_TPS79625KTTR                     | 1   |     |
| U2,U3,U4,U5                               | TMC2209_SILENTSTEPSTICK |                                                          | TMC2209_SILENTSTEPSTICK:MODULE_TMC2209_SILENTSTEPSTICK | 4   |     |
