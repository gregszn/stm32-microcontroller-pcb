# STM32 Microcontroller PCB Design

## Overview

A two-layer STM32 microcontroller PCB designed using KiCad as a hardware design project.

The board integrates an STM32G431 microcontroller, USB connectivity, 3.3V voltage regulation, an external crystal oscillator, SWD programming/debugging, and peripheral interfaces.

This project combines schematic capture, component selection, PCB layout, signal routing, power distribution, and design rule verification.

The design was developed with guidance from Phil's Lab's STM32 PCB design tutorial.

## Technologies & Tools

- **EDA Software:** KiCad 10
- **Microcontroller:** STM32G431 ARM Cortex-M4
- **Voltage Regulation:** AMS1117-3.3 linear regulator
- **Communication Interfaces:** USB, UART
- **Programming and Debugging:** SWD interface
- **PCB Design:** Two-layer PCB, copper pours, vias, and signal routing
- **Design Verification:** KiCad Design Rules Checker (DRC)
- **Visualization:** KiCad 3D Viewer and STEP models

## System Architecture

The PCB integrates the microcontroller with supporting power, clock, communication, and debugging circuitry.

1. **Power Input:** The USB connector provides a 5V input supply.
2. **Voltage Regulation:** The AMS1117-3.3 regulator converts the input voltage into a regulated 3.3V supply.
3. **Microcontroller:** The STM32G431 operates using the regulated power supply.
4. **Clock Circuit:** An external crystal oscillator provides a clock reference.
5. **USB Communication:** USB D+ and D− signals connect to the microcontroller.
6. **Programming and Debugging:** SWD connections provide access for programming and debugging.
7. **Peripheral Interfaces:** Header connections expose UART, GPIO, power, and ground signals.

## Key Features

- STM32G431 ARM Cortex-M4 microcontroller
- USB-powered 3.3V voltage regulation
- External crystal oscillator circuit
- USB data signal routing
- SWD programming and debugging interface
- UART and peripheral header connections
- BOOT selection switch and reset circuitry
- Power indicator LED
- Two-layer PCB layout with copper pours
- Four mounting holes for mechanical integration

## Technical Implementation

### Power Supply Design

The PCB uses an AMS1117-3.3 linear regulator to convert the USB 5V supply into a regulated 3.3V output.

Input and output capacitors support voltage stability and filtering.

Decoupling capacitors are placed near the STM32 power pins to support stable operation.

### Microcontroller and Clock Circuit

The STM32G431 serves as the central processing component.

An external crystal oscillator and supporting capacitors provide an external clock reference.

The design also includes reset and BOOT circuitry for microcontroller configuration.

### USB and Debugging Interfaces

The USB connector provides power and routes USB D+ and D− signals to the STM32.

An SWD interface provides connections for external programming and debugging equipment.

Additional headers expose UART and peripheral signals for future hardware development.

### PCB Layout and Routing

The board was designed using a two-layer PCB stackup in KiCad.

Components were positioned to reduce routing complexity while maintaining access to the USB connector, debugging connections, and peripheral headers.

Signal and power traces were routed using copper tracks and vias.

Copper zones were added to provide electrical connectivity and support power distribution.

## Challenges and Troubleshooting

One of the main challenges was routing signals around the STM32 microcontroller while maintaining sufficient clearance between neighboring traces, pads, and vias.

During PCB verification, KiCad's Design Rules Checker identified several issues, including:

- Via diameters below the configured minimum
- Insufficient clearance between traces and vias
- Incomplete electrical connections
- Silkscreen markings extending beyond the PCB edge

These issues were addressed by adjusting via dimensions, repositioning vias, completing electrical connections, and modifying silkscreen elements.

The project also required careful placement of the USB connector to align its footprint with the physical PCB edge.

After these adjustments, the design passed the electrical routing checks with no clearance errors or unconnected items.

## Hardware Implementation

### 3D PCB Visualization

**Front View**

<img src="images/pcb_3d_front.png" width="200" alt="STM32 PCB Front View">

**Back View**

<img src="images/pcb_3d_back.png" width="200" alt="STM32 PCB Back View">

### PCB Layout

<img src="images/pcb_layout.png" width="200" alt="STM32 PCB Layout">

### Circuit Schematic

<img src="images/schematic.png" width="200" alt="STM32 Circuit Schematic">

## Results

The completed design includes the STM32 microcontroller, regulated power supply, USB interface, external clock circuitry, debugging connections, and peripheral headers.

The PCB layout was completed in KiCad, and the final routing checks reported:

- Zero electrical clearance errors
- Zero unconnected items
- Completed power and signal routing
- Front and back 3D PCB visualizations

The project provided practical experience in schematic development, PCB routing, component footprint management, copper zone configuration, and design rule verification.

**The project is currently at the design stage. Physical PCB fabrication, assembly, and hardware testing have not yet been performed.**

## Project Files

- `STM32 PCB.kicad_pro` — KiCad project configuration
- `STM32 PCB.kicad_sch` — Circuit schematic
- `STM32 PCB.kicad_pcb` — PCB layout
- `images/` — PCB renders, layout, and schematic screenshots

## Future Improvements

- Fabricate and assemble the PCB.
- Verify the regulated 3.3V power supply.
- Test STM32 programming and debugging through SWD.
- Validate USB communication and UART functionality.
- Develop embedded firmware for peripheral testing.
- Perform hardware measurements using an oscilloscope and digital multimeter.
- Evaluate power integrity and signal quality.

## Reference

This project was developed as a tutorial-guided PCB design exercise using the following resource:

**Phil's Lab — KiCad 6 STM32 PCB Design Full Tutorial (#65)**

https://www.youtube.com/watch?v=aVUqaB0IMh4

The tutorial provided guidance on STM32 circuit architecture, schematic development, component placement, and PCB routing.

## License

This project is licensed under the MIT License.
