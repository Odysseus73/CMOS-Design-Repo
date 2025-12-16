Telescopic CMOS Operational Amplifier

SkyWater 130nm (Sky130A) | Xschem | NGSpice

📌 Project Overview

This repository documents the design and AC performance evaluation of a Telescopic CMOS Operational Amplifier implemented using the SkyWater 130nm (Sky130A) Process Design Kit.

The schematic is developed in Xschem, and all simulations are carried out using NGSpice. The project primarily focuses on analyzing the high-gain behavior, frequency response, and the impact of biasing conditions and transistor sizing (W/L ratios) on overall amplifier performance.

🛠️ Tools & Technology

Xschem – Schematic capture

NGSpice – Analog circuit simulation

SkyWater 130nm (Sky130A) PDK – CMOS device models

Linux – Simulation environment

🧩 Circuit Architecture

The telescopic operational amplifier is a single-stage, high-gain topology that employs cascoding to enhance output resistance and voltage gain.

🔹 Main Building Blocks

NMOS differential input pair

NMOS and PMOS cascode transistors

Constant tail current bias source

Single-ended output node

🔹 Key Characteristics

High intrinsic voltage gain

Low power consumption

Reduced output swing compared to two-stage op-amps

Suitable for high-speed analog applications

⚙️ Simulation Setup
AC Analysis

Small-signal AC analysis is performed to study the gain–frequency response of the amplifier.

.ac dec 100 1 1e9


This command sweeps the frequency logarithmically from 1 Hz to 1 GHz.

📂 Model File Inclusion

The Sky130 transistor models are included using the following directive:

.lib <path_to_sky130_models>/sky130.lib.spice tt


Ensure the correct path to the Sky130 model file is specified.

📈 Simulation Results
🔹 Initial Gain–Frequency Response

Moderate DC gain

Early gain roll-off

Bandwidth limited due to initial biasing and transistor sizing

🔹 Optimized Gain–Frequency Response

After tuning:

Bias voltages

Tail current

Transistor W/L ratios

The amplifier exhibits:

Improved DC gain

Extended bandwidth

Better overall AC performance

✅ Performance Summary (Qualitative)
Parameter	Observation
DC Gain	Improved after bias and W/L optimization
Bandwidth	Increased
Power Consumption	Low (single-stage design)
Stability	Inherently stable due to dominant pole
🧠 Design Insights

Cascoding significantly increases output resistance, resulting in higher gain

Proper biasing is essential to:

Keep all transistors in saturation

Maximize small-signal gain

Telescopic op-amps trade output voltage swing for higher speed and gain

Single-stage architecture eliminates the need for Miller compensation

📚 Learning Outcomes

Understanding telescopic CMOS op-amp architecture

Hands-on experience with the Sky130A PDK

Insight into biasing and transistor sizing effects

Performing AC analysis using NGSpice

📄 License & Usage

This project is intended strictly for educational and academic purposes.

🔍 Locating the Sky130 Model File (Linux)

To locate the Sky130 model file (sky130.lib.spice) on your Linux system, use:

sudo find / -type f -name "sky130.lib.spice" 2>/dev/null


Copy the appropriate file path and include it in the schematic or netlist.

📊 Plotting Frequency Response in NGSpice

After running the simulation, execute the following command in the NGSpice terminal:

plot db(v(vout)/v(vip))


Replace vout and vip with the actual node names used in your schematic.
