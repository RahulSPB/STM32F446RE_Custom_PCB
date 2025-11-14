---

# **STM32F446RE – Custom 4-Layer Development Board**

A custom-designed development board built around the **STM32F446RE** microcontroller, featuring stable power architecture, clean signal routing, multiple communication interfaces, and onboard peripherals for embedded systems development.

---

## **📌 Overview**

This project contains the complete hardware design for a **4-layer STM32F446RE development board**, built for firmware experimentation, sensor interfacing, and peripheral testing.
The board includes a solid ground plane, dedicated power plane, USB-C input, ESD protection, and connectors for UART, I²C, SPI, and SWD.

This repository includes:

* KiCad source files
* Schematic PDF
* Fabrication-ready Gerbers
* 3D renders
* Board overview and design notes

---

## **🧠 Key Features**

### **Microcontroller**

* STM32F446RE (Cortex-M4 @ 180 MHz)
* 512 KB Flash, 128 KB SRAM
* Full peripheral support: UART, SPI, I²C, ADC, Timers, DMA, GPIO

### **Clocking**

* High-Speed External Oscillator (HSE)
* Crystal placed with proper layout guidelines

### **Power System**

* USB-C power input
* AMS1111-3.3 LDO (VBUS → 3.3V)
* 5V rail available for USB
* Decoupling caps at every VDD pin
* Ferrite bead for noise filtering
* Polyfuse protection on VBUS
* Power LED indicator

### **Connectivity**

* **UART** – 4-pin header
* **I²C** – 4-pin header
* **SPI** – 10-pin header
* **SWD** – 4-pin debug/programming header
* Onboard **Si7021** temp/humidity sensor (I²C)
* LCD interface for 16×2 / 20×4 displays

---

## **🔧 PCB Stackup & Layout**

### **4-Layer Stackup**

* **Layer 1 (Top):** Signal
* **Layer 2:** Solid Ground Plane
* **Layer 3:** Power Plane (3.3V, 5V, VBUS islands)
* **Layer 4 (Bottom):** Signal

### **Routing Strategy**

* 0.3 mm trace width for general signals
* 0.5–0.6 mm for power & ground
* High-frequency noise minimized with ferrite bead
* Stitching vias across ground and power areas
* VBUS isolated to regulator & USB-C region

---

## **📁 Repository Structure**

```
stm32f446re_custom_pcb/
│
├── hardware/
│   ├── kicad_project/          # Main KiCad project files
│   ├── gerbers/                # Gerber files for fabrication
│   └── gerbers.zip             # Fabrication-ready ZIP
│   
├── documentation/
│   ├── schematic.pdf           # Full schematic
│   ├── pcb_3d_renders/         # 3D images of the PCB
│   └── board_overview.md       # Detailed design description
│
└── README.md                   # You are here
```

---

## **🛠 Tools Used**

* KiCad
* EasyEDA (optional early drafts)
* 3D Viewer & Gerber viewer
* USB-C reference design
* ST AN2606 / Datasheet guidelines

---

## **📐 Getting the Files Manufactured**

1. Download **gerbers.zip**
2. Upload to PCBWay / JLCPCB / OSHPark
3. Select **4-layer PCB**
4. Use default stackup unless otherwise stated
5. Confirm drill sizes & clearances

---

## **📸 Preview**

Screenshots of 3D renders:
(Add your `top_view.png`, `bottom_view.png`, etc. here)

```
documentation/pcb_3d_renders/
│── top_view.png
│── bottom_view.png
│── angled_view.png
```

---

## **📎 Notes**

* Boot0 is set via pull-down resistor (no switch)
* NRST uses a push-button reset switch
* Power, ground, and critical lines follow recommended ST layout guidelines
* Board is designed for HAL-based STM32 firmware development

---

## **📧 Contact**

If you want a contact section at the bottom:

```
Developer: Rahul Bagathi  
Email: Bagathi_ug_24@ei.nits.ac.in 
LinkedIn:https://www.linkedin.com/in/bagathi-rahul-b27411371 
GitHub: https://github.com/RahulSPB

```

