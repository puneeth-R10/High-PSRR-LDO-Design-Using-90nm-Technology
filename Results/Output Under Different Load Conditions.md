# Output Under Different Load Conditions
<p align="center">
<img width="1600" height="900" alt="Image" src="https://github.com/user-attachments/assets/0ae45c00-07d6-4183-96ba-890f721d3863" />
  <br>
  <em>[Figure 15: Output Under Different Load Conditions Plot ]</em>
</p>



Figure 15 shows the **DC transfer characteristics of the proposed CMOS LDO regulator under different load current conditions**. In this analysis, the input supply voltage ($V_{DD}$) is swept from **0 V to 3 V**, while the load current is varied from **0 µA to 100 µA**. The objective is to verify the regulator's ability to maintain a constant output voltage under different loading conditions and to evaluate the effect of load current on the regulation point.

The load currents used in the simulation are:

<div align="center">

<table>
<tr>
<th>Curve</th>
<th>Load Current</th>
</tr>

<tr>
<td align="center">Red</td>
<td align="center">0 µA</td>
</tr>

<tr>
<td align="center">Yellow</td>
<td align="center">25 µA</td>
</tr>

<tr>
<td align="center">Green</td>
<td align="center">50 µA</td>
</tr>

<tr>
<td align="center">Cyan</td>
<td align="center">75 µA</td>
</tr>

<tr>
<td align="center">Blue</td>
<td align="center">100 µA</td>
</tr>

</table>

</div>

---

# Purpose of this Analysis

This simulation is performed to investigate:

* Output voltage variation with load current.
* Regulated operating region.
* Dropout behavior under different loads.
* Load-driving capability of the pass transistor.
* Robustness of the feedback loop.

An ideal LDO should maintain the same output voltage irrespective of load current.

---

# Observation from the Graph

The graph can be divided into two operating regions:

## Region 1: Startup / Dropout Region

For

$$
V_{DD}<1.7V
$$

the output voltage increases almost linearly with the input voltage.

In this region:

* The pass transistor PM3 is fully ON.
* The error amplifier lacks sufficient headroom.
* Closed-loop regulation has not yet been established.

Therefore:

$$
V_{OUT}\approx V_{DD}-V_{DO}
$$

The regulator behaves like a simple pass device.

---

## Region 2: Regulation Region

At approximately:

$$
V_{DD}=1.71V
$$

all curves reach the regulation point.

Marker M1 indicates:

$$
V_{DD}=1.71V
$$

$$
V_{OUT}=1.70421V
$$

Beyond this point, the output voltage remains nearly constant even when:

$$
V_{DD}
$$

continues increasing up to 3 V.

This demonstrates successful closed-loop regulation.

---

# Regulated Output Voltage

From the graph:

$$
V_{OUT}
\approx 1.704V
$$

for all load currents.

Thus,

$$
V_{OUT}
=
1.704V
$$

is the regulated output voltage of the designed LDO.

---

# Effect of Load Current

The most important observation is that all curves almost overlap in the regulation region.

This indicates:

$$
\Delta V_{OUT}
\approx 0
$$

for different values of:

$$
I_{LOAD}
$$

---

## Physical Interpretation

As load current increases:

$$
I_{LOAD}\uparrow
$$

the pass transistor PM3 supplies more current.

The feedback loop automatically adjusts the PM3 gate voltage such that:

$$
V_{fed}=V_{ref}
$$

Therefore the output voltage remains nearly unchanged.

---

# Verification of Load Regulation

Load regulation is defined as:

$$
\text{Load Regulation}
=
\frac{\Delta V_{OUT}}
{\Delta I_{LOAD}}
$$

From the graph, the output variation among all load currents is extremely small (only a few hundred microvolts).

Hence:

$$
\text{Load Regulation}
\approx 1\text{–}2\,mV/mA
$$

which agrees with the load regulation results obtained previously.

---

# Determination of Dropout Voltage

The regulation point occurs near:

$$
V_{DD}=1.71V
$$

while

$$
V_{OUT}=1.704V
$$

Therefore:

$$
V_{DO}
=
V_{DD}-V_{OUT}
$$

$$
1.71-1.70421
$$

$$
0.00579V
$$

$$
5.79mV
$$

This point represents the minimum voltage headroom required for the regulator to begin regulating. In practice, the effective dropout measured under load is typically higher and is better evaluated using the dedicated dropout analysis.

---

# Why Curves Shift Slightly with Load?

Small separation among the curves occurs because of:

### Pass Transistor Resistance

$$
R_{DS(on)}
$$

causes a small voltage drop at higher currents.

---

### Finite Loop Gain

The error amplifier has finite DC gain.

Therefore a tiny regulation error remains.

---

### Output Resistance

The regulator output is not perfectly ideal.

$$
R_{OUT}
=
\frac{\Delta V_{OUT}}
{\Delta I_{LOAD}}
$$

which produces a small voltage variation.

---

# Performance Evaluation

The nearly overlapping curves indicate:

 Strong feedback action

 Excellent load regulation

 Stable operation

 Adequate current-driving capability

 Low sensitivity to load changes

---

# Role of Major Blocks

### Error Amplifier

* Detects output voltage variation.
* Generates correction signal.

### PMOS Pass Transistor (PM3)

* Supplies load current.
* Adjusts conduction according to load demand.

### Feedback Divider (R1–R2)

* Samples output voltage.
* Maintains regulation condition:

$$
V_{fed}=V_{ref}
$$

### Miller Compensation (Rc–Cc)

* Ensures loop stability.
* Prevents oscillation at all load conditions.

### Output Capacitor (Cout)

* Improves transient response.
* Stabilizes output voltage during load changes.

