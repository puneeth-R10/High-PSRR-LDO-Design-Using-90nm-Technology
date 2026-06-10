# Gain Plot at VDD Corners
<p align="center">
<img width="1600" height="900" alt="Image" src="https://github.com/user-attachments/assets/9e39bd73-8d64-4344-88ec-61e8c5304065" />
  <br>
  <em>[Figure 16: Gain Plot at VDD Corners ]</em>
</p>


Figure 16 shows the **loop gain response of the proposed CMOS LDO regulator under different supply voltage (VDD) corners, process corners, and temperature variations**. This analysis is performed to verify that the regulator maintains sufficient gain and stable operation across manufacturing and environmental variations.

The plotted curves represent combinations of:

* **Process Corners:** SS, TT, FF
* **Supply Voltages:** 1.8 V and 1.9 V
* **Temperatures:** -24°C, 27°C, and 125°C

This is a critical robustness test because transistor parameters vary significantly with process, voltage, and temperature (PVT) conditions.

---

# Purpose of VDD Corner Analysis

The objectives of this analysis are:

* Verify loop gain robustness.
* Evaluate process sensitivity.
* Ensure regulation under worst-case conditions.
* Confirm stability margins across all operating conditions.
* Verify that the error amplifier maintains sufficient gain.

---

# Understanding the Plot

The graph shows:

### X-axis

Frequency (Hz)

$$
10^0 \rightarrow 10^{10}\,Hz
$$

---

### Y-axis

Loop Gain (dB)

$$
A_{loop}(dB)
$$

---

Each colored curve corresponds to a different:

$$
(Process,\ Temperature,\ VDD)
$$

combination.

---

# Low-Frequency Gain Analysis

At low frequencies (near DC), the loop gain is maximum.

From the markers:

### Maximum Gain

Marker M3:

$$
A_{max}=77.67\,dB
$$

at

$$
f=2.063\,Hz
$$

---

### Minimum Gain

Marker M4:

$$
A_{min}=60.26\,dB
$$

at

$$
f=1.326\,Hz
$$

---

# Gain Spread Calculation

$$
\Delta A
=
A_{max}-A_{min}
$$

$$
77.67-60.26
$$

$$
17.41\,dB
$$

---

# Interpretation

The loop gain variation across all PVT corners is:

$$
17.41\,dB
$$

which is expected because:

* FF corner devices are faster.
* SS corner devices are slower.
* Temperature affects mobility.
* Supply voltage changes transistor overdrive.

Even under worst-case conditions, the gain remains above:

$$
60\,dB
$$

which is sufficient for high-performance LDO regulation.

---

# Why Gain Changes with Process Corner

## FF Corner (Fast-Fast)

Characteristics:

* Higher carrier mobility.
* Larger transconductance.

$$
g_m \uparrow
$$

Therefore:

$$
A_v=g_m r_o
$$

increases.

Result:

 Higher loop gain

Approximately:

$$
75-78\,dB
$$

---

## SS Corner (Slow-Slow)

Characteristics:

* Lower mobility.
* Lower transconductance.

$$
g_m \downarrow
$$

Result:

* Reduced gain.

Approximately:

$$
60-65\,dB
$$

---

## TT Corner (Typical-Typical)

Produces intermediate gain values.

---

# Effect of Supply Voltage Variation

The simulations include:

$$
V_{DD}=1.8V
$$

and

$$
V_{DD}=1.9V
$$

Higher supply voltage produces:

$$
V_{OV}
=
V_{GS}-V_{TH}
$$

increase.

Consequently:

$$
g_m
$$

increases slightly.

Result:

* Higher loop gain.
* Improved drive capability.

This explains why the 1.9 V curves are generally above the 1.8 V curves.

---

# Effect of Temperature Variation

Simulated temperatures:

$$
-24^\circ C
$$

$$
27^\circ C
$$

$$
125^\circ C
$$

---

### Low Temperature

Carrier mobility increases.

$$
\mu_n,\mu_p \uparrow
$$

Result:

Higher gain.

---

### High Temperature

Carrier mobility decreases.

$$
\mu_n,\mu_p \downarrow
$$

Result:

Lower gain.

---

# Mid-Frequency Behavior

From approximately:

$$
10^2Hz
\rightarrow
10^5Hz
$$

all curves show a smooth gain roll-off.

This behavior is caused by:

### Dominant Pole

Created by:

* Miller capacitor ($C_c$)
* High impedance internal node

The dominant pole ensures:

* Stable operation
* Predictable gain reduction

---

# High-Frequency Behavior

Above:

$$
10^7Hz
$$

the gain decreases rapidly.

The additional roll-off is caused by:

### Non-Dominant Poles

Produced by:

* Second gain stage
* PMOS pass transistor
* Output capacitor
* Parasitic capacitances

---

The gain eventually falls below:

$$
0dB
$$

which determines the unity-gain frequency of the loop.

---

# Why This Result is Important

The most important observation is:

### All Curves Follow Similar Shape

No curve exhibits:

 Gain peaking

 Sudden resonance

 Instability

 Unexpected frequency shifts

This indicates:

* Proper compensation design.
* Robust Miller compensation.
* Stable operation across PVT corners.

---

# Impact on LDO Performance

Because all corners maintain:

$$
A_{loop}>60dB
$$

the regulator preserves:

### Good Line Regulation

$$
\Delta V_{OUT}
=
\frac{\Delta V_{IN}}
{1+A_{loop}}
$$

Large loop gain minimizes output variation.

---

### Good Load Regulation

$$
\Delta V_{OUT}
=
\frac{\Delta I_{LOAD}}
{g_m(1+A_{loop})}
$$

Higher gain improves load regulation.

---

### High PSRR

$$
PSRR \propto A_{loop}
$$

Larger loop gain results in better supply-noise rejection.

---

# Verification of Robustness

The gain plot confirms that the proposed LDO:

 Functions correctly at all process corners.

 Operates across the full temperature range.

 Maintains sufficient gain at both supply voltages.

 Preserves regulation accuracy.

 Remains suitable for fabrication.


