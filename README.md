# Multi-Channel Digital Storage Oscilloscope (DSO)

A custom **Multi-Channel Digital Storage Oscilloscope (DSO)** designed using the **STM32F103C8T6** microcontroller. This project combines a custom analog front-end, trigger circuitry, anti-alias filtering, multi-channel acquisition architecture, and a TFT display into a compact oscilloscope platform.

The analog signal conditioning was designed and verified in **LTspice**, while the complete hardware was developed in **KiCad**, including schematic capture, PCB layout, and 3D visualization.

---

# Features

- Multi-channel analog acquisition architecture
- Custom analog front-end
- Input over-voltage protection
- Adjustable gain stage
- DC offset stage
- Hardware trigger comparator
- RC anti-alias filter
- STM32F103 ADC interface
- TFT display interface
- SWD programming and debugging
- Two-layer PCB
- LTspice verified analog stages

---

# Hardware Specifications

| Parameter | Specification |
|-----------|---------------|
| MCU | STM32F103C8T6 |
| ADC | 12-bit Internal ADC |
| Channels | Multi-Channel Architecture |
| Input Protection | TVS + Schottky Clamp |
| Trigger | Hardware Comparator |
| Anti-Alias Filter | RC Low Pass |
| Display | EA_eDIPTFT32-A TFT |
| Interface | I²C |
| PCB | 2-Layer |

---

# Repository Structure

```
Multi-Channel-DSO/
│
├── BOM/
│   └── DSO.xlsx
│
├── images/
│   ├── KiCad/
│   │   ├── PCB.png
│   │   ├── PCB_3D.png
│   │   ├── PCB_3D_through.png
│   │   ├── Schematic.png
│   ├── LTspice/
│   │   ├── Final_output.png
│   │   ├── Input_waveform.png
│   │   ├── Gain_waveform.png
│   │   ├── offset_waveform.png
│   │   └── Spice_Schematic.png
│
├── KiCad/
│   ├── DSO.kicad_pro
│   ├── DSO.kicad_sch
│   └── DSO.kicad_pcb
│
├── LTspice/
│   └── Osc_front.asc
│
└── README.md
```

---

# System Architecture

```
                Analog Input
                     │
                     ▼
             Input Protection
          (TVS + Clamp Diodes)
                     │
                     ▼
             Buffer Amplifier
                     │
                     ▼
           Programmable Gain Stage
                     │
                     ▼
              DC Offset Stage
                     │
                     ▼
           Trigger Comparator
                     │
                     ├────────► STM32 Trigger Input
                     │
                     ▼
            RC Anti-Alias Filter
                     │
                     ▼
              STM32 ADC + DMA
                     │
                     ▼
            Waveform Processing
                     │
                     ▼
                TFT Display
```

---

# Analog Signal Chain

The complete analog front-end consists of:

- Input protection
- Voltage scaling
- Buffer amplifier
- Gain amplifier
- DC offset stage
- Trigger comparator
- RC anti-alias filter
- ADC interface

The design conditions incoming analog signals into the STM32 ADC input range while maintaining waveform integrity.

---

# LTspice Simulation

The complete analog signal chain was verified before PCB implementation.

Simulation stages include:

- Input waveform
- Gain stage response
- Offset stage response
- Final conditioned output
- Complete analog schematic

---

# PCB Design

The PCB was designed using **KiCad** with emphasis on:

- Compact component placement
- Analog and digital section separation
- Ground plane implementation
- Short analog signal routing
- Decoupling capacitor placement
- SWD programming interface
- TFT display interface

---

# Development Workflow

- Analog front-end design
- LTspice verification
- Schematic capture
- PCB layout
- 3D PCB visualization
- BOM generation
- Embedded firmware development *(in progress)*
- Hardware validation *(planned)*

---

# Software Used

- KiCad 9
- LTspice
- Git
- GitHub

---

# Images

## Complete Schematic

![Schematic](images\KiCad\Schematic.png)

---

## PCB Layout

![PCB](images\KiCad\PCB.png)

---

## 3D PCB View

![PCB3D](images\KiCad\PCB_3D.png)

---

## Transparent 3D View

![PCB3DThrough](images\KiCad\PCB_3D_through.png)

---

## LTspice Schematic

![LTspice](images\LTspice\Spice_Schematic.png)

---

## Input Waveform

![Input](images\LTspice\Input_waveform.png)

---

## Gain Stage Output

![Gain](images\LTspice\Gain_waveform.png)

---

## Offset Stage Output

![Offset](images\LTspice\offset_waveform.png)

---

## Final Output Waveform

![Final](images\LTspice\Final_output.png)

---

# Future Improvements

- Dual simultaneous ADC acquisition
- External high-speed ADC
- DMA circular buffer implementation
- Auto trigger mode
- Single-shot trigger
- FFT spectrum analyzer
- USB waveform streaming
- SD card waveform storage
- Automatic measurements
- Cursor functions
- Frequency and duty-cycle measurement
- Rotary encoder user interface

---

# Author

**Aryan Kodan**

Electronics Engineering | Embedded Systems | PCB Design | Analog Circuit Design | VLSI

GitHub: https://github.com/Aryan-Kodan

---

# License

This project is released under the MIT License.