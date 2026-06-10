# Gain Plot at Process Corners Analysis
<p align="center">
<img width="1600" height="900" alt="Image" src="https://github.com/user-attachments/assets/d94a2aad-af35-49d3-a343-959f3555c8cb" />
  <br>
  <em>[Figure 17: Gain Plot at Process Corners ]</em>
</p>

Figure 17 illustrates the **loop gain response of the proposed CMOS LDO regulator under different process corners**. Process corner analysis is performed to evaluate the effect of manufacturing variations on the regulator's performance and to verify that the LDO maintains sufficient gain and stability after fabrication.

The process corners considered in this analysis are:

* **FF (Fast-Fast)** Corner
* **TT (Typical-Typical)** Corner
* **SS (Slow-Slow)** Corner

along with temperature variations and supply voltage variations.

---

# What are Process Corners?

During IC fabrication, transistor parameters vary due to unavoidable manufacturing tolerances.

The major parameters affected are:

* Threshold voltage ($V_{TH}$)
* Carrier mobility ($\mu$)
* Oxide thickness
* Channel dimensions
* Transconductance ($g_m$)

To model these variations, foundries provide process corner models.

---

## FF Corner (Fast-Fast)

Both NMOS and PMOS transistors are faster than nominal.

Characteristics:

$$
g_m \uparrow
$$

$$
I_D \uparrow
$$

$$
R_{ON} \downarrow
$$

Result:

* Higher gain
* Higher bandwidth
* Faster transient response

---

## TT Corner (Typical-Typical)

Represents nominal manufacturing conditions.

Characteristics:

* Typical mobility
* Typical threshold voltage
* Typical gain

Used as the reference corner.

---

## SS Corner (Slow-Slow)

Both NMOS and PMOS devices are slower than nominal.

Characteristics:

$$
g_m \downarrow
$$

$$
I_D \downarrow
$$

Result:

* Lower gain
* Lower bandwidth
* Worst-case regulation accuracy

---

# Purpose of Process Corner Analysis

The objective is to verify:

* Gain robustness
* Stability robustness
* Manufacturability
* Worst-case performance

An LDO should operate correctly under all process corners.

---

# Observation from Figure 17

The graph shows multiple gain curves corresponding to different process corners.

All curves exhibit similar behavior:

1. High DC gain at low frequencies.
2. Smooth gain roll-off.
3. Consistent pole locations.
4. No abnormal gain peaking.
5. Stable frequency response.

This indicates a robust design.

---

# Low-Frequency Gain Analysis

The low-frequency region represents the DC loop gain.

From the markers:

### Maximum Gain

Marker M3:

$$
A_{max}=77.67dB
$$

at

$$
f=2.063Hz
$$

---

### Minimum Gain

Marker M4:

$$
A_{min}=60.26dB
$$

at

$$
f=1.326Hz
$$

---

# Gain Spread

The gain variation across process corners is:

$$
\Delta A
=
A_{max}-A_{min}
$$

$$
77.67-60.26
$$

$$
17.41dB
$$
---

# Interpretation of Gain Variation

### FF Corner

Produces the highest gain.

Reason:

$$
g_m \uparrow
$$

Since amplifier gain is:

$$
A_v=g_m r_o
$$

larger transconductance increases gain.

Observed gain:

$$
75-78dB
$$

---

### TT Corner

Produces intermediate gain.

Observed gain:

$$
68-72dB
$$

---

### SS Corner

Produces the lowest gain.

Observed gain:

$$
60-65dB
$$

---

# Why Gain is Important

Loop gain directly affects:

## Line Regulation

$$
\text{Line Regulation}
\propto
\frac{1}{1+A_{loop}}
$$

Higher gain results in better line regulation.

---

## Load Regulation

$$
\text{Load Regulation}
\propto
\frac{1}{1+A_{loop}}
$$

Higher gain reduces output voltage variation.

---

## PSRR

$$
PSRR \propto A_{loop}
$$

Greater loop gain improves noise rejection.

---

# Frequency Response Analysis

## Low-Frequency Region

Frequency range:

$$
1Hz
\rightarrow
100Hz
$$

The gain remains almost constant.

This region corresponds to:

* High error amplifier gain
* Strong feedback action
* Excellent regulation

---

## Mid-Frequency Region

Frequency range:

$$
10^2Hz
\rightarrow
10^5Hz
$$

The gain decreases gradually.

This roll-off is produced by:

### Dominant Pole

Created by:

* Miller compensation capacitor ($C_c$)
* Internal high impedance node

The dominant pole ensures stable operation.

---

## High-Frequency Region

Frequency range:

$$
10^7Hz
\rightarrow
10^{10}Hz
$$

The gain drops rapidly due to:

* Second-stage pole
* Output pole
* Parasitic capacitances

All curves eventually approach very low gain values.
---

# Stability Observation

An important observation is that:

### All Curves Have Similar Shape

There is:

 No excessive peaking

 No resonance

 No abrupt pole movement

 No instability

This indicates that the compensation network:

$$
R_c-C_c
$$

is robust across all process corners.

---

# Impact on LDO Performance

Even under the worst-case SS corner:

$$
A_{loop}>60dB
$$

which is generally sufficient for:

* Accurate output regulation
* Good PSRR
* Stable operation
* Fast transient response

Therefore the regulator remains functional under manufacturing variations.

---

# Verification of Design Robustness

The process corner analysis confirms that:

### FF Corner

* Highest gain
* Best regulation

### TT Corner

* Nominal performance

### SS Corner

* Lowest gain
* Worst-case operation

Despite these variations:

$$
60dB
\le
A_{loop}
\le
78dB
$$

which is more than adequate for LDO applications.

