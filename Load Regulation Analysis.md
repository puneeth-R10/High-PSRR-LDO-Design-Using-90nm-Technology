# Load Regulation Analysis

<p align="center">
 <img width="1600" height="900" alt="Image" src="https://github.com/user-attachments/assets/ed3b744c-7145-4c90-9dde-15a52a1c507e" />
  <br>
  <em>[Figure 12: Load Regulation Analysis ]</em>
</p>

Figure 12 shows the **load regulation characteristics** of the proposed CMOS LDO regulator obtained from DC sweep analysis in Cadence Virtuoso. In this simulation, the load current is varied while the input voltage and reference voltage are kept constant. The purpose of this analysis is to evaluate the ability of the regulator to maintain a constant output voltage under varying load conditions.

---

## What is Load Regulation?

Load regulation measures the change in output voltage due to a change in load current.

Mathematically:

**Load Regulation = ΔV<sub>OUT</sub> / ΔI<sub>LOAD</sub>**

### Units

- V/A
- mV/mA
- µV/µA

A smaller value indicates better regulation capability.

---

## Importance of Load Regulation

In practical applications, load current continuously changes.

### Examples

- Microprocessor switching activity
- Sensor operation
- RF transmission
- ADC/DAC conversion

An ideal LDO should maintain:

**V<sub>OUT</sub> = Constant**

irrespective of load current variations.

Good load regulation ensures:

- Stable output voltage
- Reduced voltage droop
- Better system reliability
- Improved analog circuit performance

---

## Observation from Figure 12

The graph plots:

**V<sub>OUT</sub>**

versus

**I<sub>LOAD</sub>**

from approximately:

**0 µA → 250 µA**

The output voltage decreases slightly as load current increases.

This behavior is expected because increasing load current causes:

- Increased voltage drop across the pass transistor
- Finite output resistance of the regulator
- Small regulation error in the feedback loop

However, the variation is extremely small, indicating excellent load regulation.

---

## Measured Data from the Graph

### Marker M80

**I<sub>LOAD1</sub> = 92.47688 µA**

**V<sub>OUT1</sub> = 1.702656 V**

---

### Marker M81

**I<sub>LOAD2</sub> = 120.224 µA**

**V<sub>OUT2</sub> = 1.702621 V**

---

## Step 1: Calculate Change in Output Voltage

**ΔV<sub>OUT</sub> = V<sub>OUT1</sub> − V<sub>OUT2</sub>**

**ΔV<sub>OUT</sub> = 1.702656 − 1.702621**

**ΔV<sub>OUT</sub> = 0.000035 V**

**ΔV<sub>OUT</sub> = 35 µV**

---

## Step 2: Calculate Change in Load Current

**ΔI<sub>LOAD</sub> = I<sub>LOAD2</sub> − I<sub>LOAD1</sub>**

**ΔI<sub>LOAD</sub> = 120.224 − 92.47688**

**ΔI<sub>LOAD</sub> = 27.74712 µA**

---

## Step 3: Calculate Load Regulation

**Load Regulation = ΔV<sub>OUT</sub> / ΔI<sub>LOAD</sub>**

Substituting values:

**Load Regulation = 35 µV / 27.74712 µA**

**Load Regulation = 1.261 V/A**

---

## Converting Units

### In mV/mA

**1.261 V/A = 1.261 mV/mA**

---

### In µV/µA

**1.261 µV/µA**

---

## Final Load Regulation

**Load Regulation = 1.261 V/A**

or

**Load Regulation = 1.261 mV/mA**

or

**Load Regulation = 1.261 µV/µA**

---

## Alternative Full-Range Calculation

From the graph:

### At No Load

**V<sub>OUT,max</sub> ≈ 1.70278 V**

### At Maximum Load

**V<sub>OUT,min</sub> ≈ 1.70245 V**

### Output Change

**ΔV<sub>OUT</sub> = 1.70278 − 1.70245**

**ΔV<sub>OUT</sub> = 0.00033 V**

**ΔV<sub>OUT</sub> = 330 µV**

### Load Current Change

**ΔI<sub>LOAD</sub> = 250 µA**

Therefore:

**Load Regulation = 330 µV / 250 µA**

**Load Regulation = 1.32 V/A**

**Load Regulation = 1.32 mV/mA**

This closely matches the marker-based calculation.

---

## Why Does Output Voltage Drop with Load Current?

When load current increases:

**I<sub>LOAD</sub> ↑**

more current must flow through PM3.

The pass transistor has finite resistance:

**R<sub>DS(on)</sub>**

Therefore:

**V<sub>drop</sub> = I<sub>LOAD</sub> × R<sub>DS(on)</sub>**

increases slightly.

Consequently:

**V<sub>OUT</sub>**

decreases by a very small amount.

The feedback loop immediately attempts to compensate by increasing PM3 conduction.

Because the loop gain is finite, a tiny residual error remains.

---

## Relationship with Output Resistance

Load regulation is directly related to the closed-loop output resistance:

**R<sub>OUT</sub> = ΔV<sub>OUT</sub> / ΔI<sub>LOAD</sub>**

Thus:

**R<sub>OUT</sub> = 1.261 Ω**

A small output resistance indicates strong regulation capability.

---

## Role of Individual Blocks

### Error Amplifier

- Detects output voltage changes
- Generates correction signal

### PMOS Pass Transistor (PM3)

- Supplies additional current when load increases
- Maintains regulated output voltage

### Feedback Divider (R1-R2)

- Senses output voltage continuously
- Forces:

**V<sub>fed</sub> = V<sub>ref</sub>**

### Compensation Network (R<sub>c</sub>-C<sub>c</sub>)

- Maintains loop stability
- Prevents oscillation during load variations

### Output Capacitor (C<sub>out</sub>)

- Supplies transient current
- Minimizes output voltage droop

---

## Performance Evaluation

<div align="center">

<table>
<tr>
<th>Load Regulation</th>
<th>Performance</th>
</tr>

<tr>
<td>&gt; 10 mV/mA</td>
<td>Poor</td>
</tr>

<tr>
<td>1–10 mV/mA</td>
<td>Good</td>
</tr>

<tr>
<td>&lt; 2 mV/mA</td>
<td>Excellent</td>
</tr>

</table>

</div>

Obtained result:

**1.261 mV/mA**

This falls in the **Excellent** category.

---

## Summary Table

<div align="center">

<table>
<tr>
<th>Parameter</th>
<th>Value</th>
</tr>

<tr>
<td>Marker M80</td>
<td>92.4769 µA, 1.702656 V</td>
</tr>

<tr>
<td>Marker M81</td>
<td>120.224 µA, 1.702621 V</td>
</tr>

<tr>
<td>ΔV<sub>OUT</sub></td>
<td>35 µV</td>
</tr>

<tr>
<td>ΔI<sub>LOAD</sub></td>
<td>27.747 µA</td>
</tr>

<tr>
<td>Load Regulation</td>
<td>1.261 V/A</td>
</tr>

<tr>
<td>Load Regulation</td>
<td>1.261 mV/mA</td>
</tr>

<tr>
<td>Output Resistance</td>
<td>1.261 Ω</td>
</tr>

<tr>
<td>Load Current Range</td>
<td>0–250 µA</td>
</tr>

<tr>
<td>Regulation Quality</td>
<td>Excellent</td>
</tr>

</table>

</div>

---

## Conclusion

**Figure 12 illustrates the load regulation performance of the proposed CMOS LDO regulator. As the load current increases from approximately 92.48 µA to 120.22 µA, the output voltage decreases by only 35 µV. The calculated load regulation is 1.261 mV/mA, demonstrating excellent output voltage stability under varying load conditions. The result confirms the effectiveness of the high-gain error amplifier, PMOS pass transistor, feedback network, and compensation circuitry in maintaining a nearly constant output voltage despite changes in load current.**
