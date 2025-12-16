## Telescopic CMOS Operational Amplifier  
**SkyWater 130nm (Sky130A) | Xschem | NGSpice**

---

## Project Overview

This project presents the design and AC performance analysis of a **Telescopic CMOS Operational Amplifier** implemented using the **SkyWater 130nm (Sky130A) Process Design Kit**.

The schematic is created in **Xschem**, and simulations are performed using **NGSpice**. The primary goal is to study the amplifier’s **high-gain behavior**, **frequency response**, and the effect of **bias voltages**, **tail current**, and **transistor sizing (W/L ratios)** on overall performance.

---

## Tools & Technology

- **Xschem** – Schematic capture  
- **NGSpice** – Circuit simulation  
- **SkyWater 130nm (Sky130A) PDK** – CMOS transistor models  
- **Linux** – Simulation environment  

---

## Circuit Architecture

The telescopic operational amplifier is a **single-stage, high-gain topology** that employs **cascoding** to increase output resistance and voltage gain.

### Main Building Blocks

- NMOS differential input pair  
- NMOS and PMOS cascode transistors  
- Constant tail current bias source  
- Single-ended output node  

### Key Characteristics

- High intrinsic voltage gain  
- Low power consumption  
- Limited output swing compared to two-stage op-amps  
- Suitable for high-speed analog applications  

---

## Simulation Setup

### AC Analysis

Small-signal AC analysis is performed to evaluate the gain–frequency response of the amplifier.

```spice
.ac dec 100 1 1e9

```
## Simulation Results

### Initial Gain–Frequency Response

- Moderate DC gain observed  
- Early gain roll-off  
- Bandwidth limited due to initial biasing and transistor sizing  

### Optimized Gain–Frequency Response

After tuning the following parameters:
- Bias voltages  
- Tail current  
- Transistor W/L ratios  

The amplifier shows:
- Improved DC gain  
- Increased bandwidth  
- Enhanced overall AC performance  

---

## Performance Summary (Qualitative)

| Parameter | Observation |
|----------|-------------|
| **DC Gain** | Improved after bias and W/L optimization |
| **Bandwidth** | Increased |
| **Power Consumption** | Low (single-stage design) |
| **Stability** | Inherently stable due to dominant pole |

---

## Design Insights

- Cascoding significantly increases output resistance, leading to higher voltage gain  
- Proper biasing is essential to:
  - Maintain all MOS transistors in saturation  
  - Maximize small-signal gain  
- Telescopic op-amps trade output voltage swing for higher speed and gain  
- Single-stage architecture eliminates the need for Miller compensation  

---

## Learning Outcomes

- Understanding the telescopic CMOS operational amplifier architecture  
- Practical experience working with the Sky130A PDK  
- Insight into the impact of biasing and transistor sizing on analog performance  
- Performing AC analysis using NGSpice  

