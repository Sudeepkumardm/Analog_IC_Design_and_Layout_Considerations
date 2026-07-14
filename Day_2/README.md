# 📘 Day 2 — Common Source Amplifier & Differential Amplifier Analysis
**Analog IC Design & Layout Considerations**

## 🎯 Objective
- Design and analyze **Common Source (CS) Amplifiers**
- Compare **three circuit variants** to study gain improvement
- Study **DC response, region of operation, and transient behavior**
- Design and simulate a **Differential Amplifier**
- Strengthen understanding of **MOSFET small-signal gain and biasing**

## 🔹 Part 1 — Common Source Amplifier Gain Analysis

### 📌 Circuit 1 — Basic Common Source Amplifier
Initial implementation of a standard CS amplifier to observe baseline gain.

Here, the load resistor is large, and the voltage gain is given by:

\[
A_v = -(g_m \times R_D)
\]

![Circuit 1 Schematic](Common_Source_amplifier_gain_analysis/Analysis_1stCkt.png)

### 📌 Circuit 2 — Improved Gain Configuration
Modified transistor sizing and biasing to enhance gain performance.

The resistor is replaced with a **diode-connected transistor**, which behaves as an active load (current source). The voltage gain becomes:

\[
A_v = -\frac{g_{m1}}{g_{m2}}
\]

Although the gain improves, it is still not sufficient for the desired application.

![Circuit 2 Schematic](Common_Source_amplifier_gain_analysis/Analysis_2ndCkt.png)

### 📌 Circuit 3 — Optimized Gain Configuration
Final optimized CS amplifier with improved gain and operating region stability.

Separate bias voltages are applied to each MOSFET, allowing independent control of the operating point and resulting in higher gain.

![Circuit 3 Schematic](Common_Source_amplifier_gain_analysis/Analysis_3rdCkt.png)

## 📊 DC Gain Comparison Across Three Circuits

### 🔹 Gain for 120nm Channel Length

![DC Gain 120nm](Common_Source_amplifier_gain_analysis/DC_Response_120nm_Gain.png)

### 🔹 Gain for 1µm Channel Length

![DC Gain 1µm](Common_Source_amplifier_gain_analysis/DC_Response_1u_Gain.png)

## 📐 Gain Equation Used

\[
A_v = -g_m \times R_D
\]

Where:

- \(g_m=\dfrac{2I_D}{V_{OV}}\)
- \(R_D\) = Drain resistance
- The negative sign indicates a **180° phase inversion** between the input and output.

## 🔹 Region of Operation Verification (Circuit 3)

The MOSFET is verified to operate in the **saturation region**, which is essential for achieving maximum small-signal gain.

![Region of Operation](Common_Source_amplifier_gain_analysis/Region_3rdCkt.png)

## ⏱ Transient Response — Circuit 3

Transient simulation verifies the amplification of the input signal while maintaining the desired phase inversion.

![Transient Response](Common_Source_amplifier_gain_analysis/Transient_response_3rdckt.png)

## 🧪 Three-Circuit Comparison Summary

| Circuit | Modification | Result |
|----------|--------------|--------|
| Circuit 1 | Basic CS amplifier with resistor load | Low baseline gain |
| Circuit 2 | Diode-connected MOS active load | Higher gain |
| Circuit 3 | Independent bias voltages | **Highest gain and improved stability** |

### 📌 Key Insight

- Increasing **transconductance (\(g_m\))** improves voltage gain.
- Increasing the **channel length** increases the MOSFET output resistance, thereby improving gain.
- Proper biasing ensures the MOSFET remains in saturation for stable amplifier operation.

## 🔹 Part 2 — Differential Amplifier Design / Operational Transconductance Amplifier (OTA)

### 📌 Differential Amplifier Schematic

![Differential Amplifier Schematic](Diffrential_Amplifier/DiffAmp_Schematic.png)

### 📌 Alternate Schematic View

![Differential Amplifier Alternate Schematic](Diffrential_Amplifier/DiffAmp_Schematic1.png)

### 📊 Differential Output Response

![Differential Amplifier Output](Diffrential_Amplifier/DiffAmp_Output.png)

## 📐 Differential Gain Equation

The differential voltage gain is given by:

\[
A_d=g_m \times R_D
\]

### Common Mode Rejection Ratio (CMRR)

\[
CMRR=\frac{A_d}{A_{cm}}
\]

where:

- \(A_d\) = Differential gain
- \(A_{cm}\) = Common-mode gain

A higher **CMRR** indicates better rejection of common-mode noise.

## 🎓 Key Learnings

### Common Source Amplifier

- Voltage gain depends on **transconductance (\(g_m\))** and **load resistance**.
- Longer channel devices provide higher output resistance, improving gain.
- Proper biasing keeps the MOSFET in saturation for maximum amplification.
- Comparing multiple circuit configurations helps optimize analog amplifier performance.

### Differential Amplifier

- Amplifies only the **difference between two input signals**.
- Rejects common-mode signals and external noise.
- Forms the basic building block of **Operational Amplifiers (Op-Amps)** and many analog integrated circuits.

## 🛠 Tools Used

- Cadence Virtuoso
- Spectre Simulator
- Analog Design Environment (ADE)

## 📈 Outcome

Successfully designed and analyzed:

- **Three Common Source amplifier configurations** with comparative gain analysis.
- **A Differential Amplifier (OTA)** with differential response verification.
- Improved understanding of **MOSFET biasing, gain enhancement techniques, saturation operation, and analog circuit optimization**.
