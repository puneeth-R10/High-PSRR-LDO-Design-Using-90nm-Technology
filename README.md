# 🚀 Low Dropout CMOS Voltage Regulator (LDO) Design Using 90 nm CMOS Technology



## 📌 Project Overview

This repository presents the design and simulation of a **Low Dropout (LDO) Voltage Regulator** implemented using **90 nm CMOS technology** in **Cadence Virtuoso**. The proposed regulator employs a **two-stage error amplifier, PMOS pass transistor, Miller compensation network, and feedback control loop** to achieve low dropout operation, high stability, excellent regulation performance, and strong power supply noise rejection.

LDO regulators are essential components in modern Power Management Units (PMUs), providing clean and regulated supply voltages to sensitive analog, digital, RF, and mixed-signal circuits. They are widely used in portable electronics, IoT devices, biomedical systems, wireless communication modules, and battery-powered applications.

The proposed design delivers a regulated output voltage of **1.704 V** from a **1.8 V input supply** with a low **dropout voltage of 96 mV**, making it suitable for low-voltage and low-power integrated systems.

---

## 🎯 Project Objectives

The primary objectives of this project were:

✅ Design a low-dropout CMOS voltage regulator

✅ Achieve stable output voltage regulation

✅ Improve line and load regulation performance

✅ Obtain high loop gain and adequate phase margin

✅ Achieve strong Power Supply Rejection Ratio (PSRR)

✅ Improve transient response performance

✅ Verify stability under varying load conditions

✅ Validate operation across process, voltage, and temperature (PVT) corners

---

## 🏗️ LDO Architecture

The proposed CMOS LDO regulator consists of the following functional blocks:

### 🔹 Reference Voltage Source

Provides a stable reference voltage used as the regulation target.

---

### 🔹 Two-Stage Error Amplifier

The error amplifier continuously compares the reference voltage with the feedback voltage and generates the control signal required to regulate the output.

Functions:

* Error detection
* Voltage regulation
* Loop gain enhancement
* Stability improvement

---

### 🔹 Miller Compensation Network

A compensation network consisting of:

* Compensation Capacitor (Cc)
* Compensation Resistor (Rc)

is employed to improve stability.

Functions:

* Pole splitting
* Phase margin improvement
* Oscillation prevention
* Loop stabilization

---

### 🔹 PMOS Pass Transistor

The PMOS pass device controls the current flowing from the input supply to the output load.

Functions:

* Current regulation
* Low-dropout operation
* Output voltage control

---

### 🔹 Feedback Network

The feedback resistor divider continuously senses the output voltage and feeds a scaled version back to the error amplifier.

Functions:

* Closed-loop regulation
* Output voltage setting
* Regulation accuracy

---

### 🔹 Output Capacitor and ESR Network

The output stage contains an external capacitor and ESR component.

Functions:

* Ripple reduction
* Improved transient response
* Output stabilization
* ESR zero generation

---

## ⚙️ Design Specifications

| Parameter              | Value               |
| ---------------------- | ------------------- |
| Technology             | 90 nm CMOS          |
| Supply Voltage         | 1.8 V               |
| Output Voltage         | 1.704 V             |
| Pass Device            | PMOS                |
| Compensation Technique | Miller Compensation |
| Design Tool            | Cadence Virtuoso    |
| Simulator              | Spectre             |

---

## 🧪 Simulation and Verification

The regulator was extensively verified using Cadence Virtuoso through multiple analyses.

### 📈 Dropout Voltage Analysis

Determines the minimum voltage difference required between input and output for proper regulation.

**Obtained Dropout Voltage:**

* 96 mV

---

### 📊 Line Regulation Analysis

Evaluates output voltage variation with changes in input voltage.

**Obtained Line Regulation:**

* 0.146 mV/V

---

### 📉 Load Regulation Analysis

Evaluates output voltage variation under changing load current conditions.

**Obtained Load Regulation:**

* 1.26 mV/mA

---

### 🎵 PSRR Analysis

Measures the ability of the regulator to reject supply noise.

**Obtained Results:**

| Frequency | PSRR      |
| --------- | --------- |
| 10 kHz    | -80.76 dB |
| 100 kHz   | -80.29 dB |
| 1 MHz     | -78.39 dB |

---

### 🔄 Stability Analysis

Used to verify closed-loop stability through gain and phase margin measurements.

**Obtained Results:**

* Loop Gain = 79.02 dB
* Phase Margin = 68.65°
* Gain Margin = 79.02 dB

---

### ⚡ Line Transient Analysis

Evaluates regulator performance under sudden input voltage changes.

Results show:

* Stable operation
* Fast recovery
* No oscillations
* Controlled overshoot

---

### 🔋 Load Transient Analysis

Evaluates output response under sudden load current changes.

Obtained Results:

* Overshoot = 0.5 mV
* Undershoot = 0.5 mV
* Settling Time = 5 µs

---

### 🌍 PVT Corner Analysis

The regulator was verified under:

#### Process Corners

* FF (Fast-Fast)
* FS (Fast-Slow)
* SF (Slow-Fast)
* SS (Slow-Slow)
* TT (Typical-Typical)

#### Supply Voltage Corners

* 1.8 V
* 1.9 V

#### Temperature Corners

* 40°C to 125°C

The design remained stable across all tested conditions.

---

## 📷 Repository Contents

This repository includes:

📌 Block Diagram

📌 Cadence Schematic

📌 Error Amplifier Design

📌 Stability Analysis

📌 Dropout Analysis

📌 Line Regulation Results

📌 Load Regulation Results

📌 PSRR Results

📌 Line Transient Analysis

📌 Load Transient Analysis

📌 Process Corner Analysis

📌 PVT Verification Results

📌 Project Documentation

---

## ✨ Key Highlights

🔹 Low Dropout Voltage (96 mV)

🔹 High Loop Gain (79.02 dB)

🔹 Excellent PSRR Performance

🔹 Strong Closed-Loop Stability

🔹 High Phase Margin (68.65°)

🔹 Fast Transient Response

🔹 Stable Across PVT Variations

🔹 Miller Compensation Based Design

🔹 Low-Power CMOS Implementation

🔹 Cadence Virtuoso Based Design Flow

---

## 🎓 Learning Outcomes

Through this project, I gained practical experience in:

* Analog IC Design
* CMOS Circuit Design
* LDO Architecture Development
* Error Amplifier Design
* Frequency Compensation Techniques
* Stability Analysis
* PSRR Optimization
* Line and Load Regulation Analysis
* Transient Response Analysis
* PVT Corner Verification
* Cadence Virtuoso Design Flow
* Spectre Simulation Environment
* Power Management Circuit Design

---

## 💡 Applications

The proposed CMOS LDO regulator can be used in:

📱 Portable Electronics

🌐 IoT Devices

🏥 Biomedical Systems

📡 Wireless Communication Modules

🔋 Battery-Powered Applications

⚙️ Power Management Units (PMUs)

🖥️ Mixed-Signal Integrated Circuits

📊 ADC and DAC Power Supplies

🚀 Low-Power Embedded Systems

---

## 🛠️ Tools Used

* Cadence Virtuoso
* Spectre Simulator
* 90 nm CMOS Technology
* Analog Design Methodology
* Power Management Design Techniques

---

## ⭐ Conclusion

The proposed CMOS LDO regulator implemented in 90 nm technology successfully achieves low-dropout operation while maintaining excellent voltage regulation, strong noise rejection, and robust loop stability. The regulator delivers a regulated output voltage of 1.704 V from a 1.8 V supply with a dropout voltage of only 96 mV. It achieves a loop gain of 79.02 dB, a phase margin of 68.65°, and PSRR values better than −78 dB across a wide frequency range. Extensive simulations including line regulation, load regulation, transient response, stability analysis, and PVT verification confirm the effectiveness and robustness of the design, making it suitable for modern low-power integrated power management applications.


## ⭐ Acknowledgement

Special thanks to the faculty members, project guide, and team members whose guidance and support contributed to the successful completion of this work.

---

### If you found this project useful, consider giving it a ⭐ on GitHub.

