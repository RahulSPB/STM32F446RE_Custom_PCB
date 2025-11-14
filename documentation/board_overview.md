# **STM32F446RE – 4-Layer Custom Development Board**

### **Board Overview**

This custom 4-layer PCB is designed around the **STM32F446RE** microcontroller for reliable embedded systems development, sensor interfacing, and firmware experimentation. The design emphasizes clean power delivery, low-noise routing, and robust peripheral expansion, following industry-standard PCB practices.

---

## **Core Specifications**

### **Microcontroller**

* **STM32F446RE** (ARM Cortex-M4 @ 180 MHz)
* 512 KB Flash, 128 KB SRAM
* Rich peripheral set: UART, I²C, SPI, ADC, Timers, DMA, GPIO, etc.

### **Clocking**

* **High-Speed External Oscillator (HSE)** for accurate system timing
* Crystal placed with proper guard traces and decoupling

### **Boot & Reset**

* **BOOT0 pulled down via resistor** (no switch used)
* **NRST** connected to a classic push-button reset switch
* Reset line filtered and referenced cleanly to ground

---

## **Power Architecture**

### **Input & Regulation**

* **USB-C port** used as primary power input
* **AMS1117-3.3V LDO** converts VBUS → 3.3V
* 5V rail available for USB and related peripherals
* VBUS kept isolated to a small controlled island feeding the regulator

### **Filtering & Stability**

* Decoupling capacitors placed at every VDD pin (0.1µF + bulk caps)
* **Ferrite bead** used for high-frequency noise suppression
* **Polyfuse** protection at USB-C input
* Clean ground return paths ensured through layer stackup

### **ESD Protection**

* ESD diode protection on USB-C and sensitive I/O lines
* Safe spacing and return path planning to support surge handling

### **Indicators**

* **Power LED** connected to 3.3V rail for power-on indication

---

## **Connectivity & Interfaces**

### **Communication Headers**

Modular connectors for peripheral expansion:

* **UART** – 4-pin header
* **I²C** – 4-pin header
* **SPI** – 10-pin header
* **SWD** – 4-pin programming/debug header

All connectors arranged with consistent VCC/GND ordering for easy interfacing.

### **On-Board Peripherals**

* **Si7021** Temperature & Humidity Sensor (I²C)
* **LCD Interface** (compatible with 16x2 / 20x4 displays)
* Clean routing of sensor and display lines for minimal noise

---

## **PCB Layout & Stackup**

### **Layer Stack**

* **Layer 1 (Top Layer):** Signal routing
* **Layer 2 (Inner Layer 1):** **Solid Ground Plane** (continuous GND reference)
* **Layer 3 (Inner Layer 2):** **Dedicated Power Plane**

  * Independent regions for **3.3V**, **5V**, and **VBUS**
  * 3.3V used across most of the board
  * 5V confined to USB-related sections
  * VBUS limited to the regulator and USB-C island
* **Layer 4 (Bottom Layer):** Signal routing

### **Routing Rules**

* **0.3 mm trace width** for standard signal lines
* **0.5–0.6 mm traces** for power and ground
* Controlled routing to minimize crosstalk and ensure integrity

### **Via Strategy**

* **Stitching vias** placed across all ground and power areas
* Ground plane stitched densely to improve return paths
* Power planes also stitched for low-impedance delivery
* No unnecessary connections to planes — only GND and power vias used

This ensures clean current flow, reduced ground bounce, and improved EMI performance.

---

## **Design Goals**

* Stable power distribution
* Low-noise routing for digital & analog peripherals
* Flexible expansion via UART, I²C, SPI, and SWD
* Professional-grade 4-layer design suitable for real firmware work
* Robustness through ESD protection, filtering, and proper decoupling

---

## **Repository Contents**

* KiCad project files (`.kicad_sch`, `.kicad_pcb`, `.kicad_pro`)
* Schematic PDF
* Gerber & drill files + ZIP for fabrication
* 3D renders of the board
* Board documentation and layout notes

---

