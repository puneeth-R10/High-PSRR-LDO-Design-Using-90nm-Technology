# Line Regulation Analysis.

<p align="center">
 <img width="1600" height="900" alt="Image" src="https://github.com/user-attachments/assets/cd502d31-002e-40e9-b0ff-b506797601b1" />
  <br>
  <em>[Figure 11: Expansion of Block Diagram of proposed LDO ]</em>
</p>


Figure 11 shows the **DC Line Regulation characteristic** of the proposed CMOS LDO regulator. In this analysis, the input voltage (**V<sub>IN</sub>**) is swept from approximately **1.6 V to 2.0 V**, while the load current remains constant. The objective is to evaluate the ability of the regulator to maintain a constant output voltage despite variations in the supply voltage.

---

## What is Line Regulation?

Line regulation measures how much the output voltage changes when the input voltage changes.

Mathematically:

**Line Regulation = ΔV<sub>OUT</sub> / ΔV<sub>IN</sub>**

Usually expressed as:

- mV/V
- µV/V

A smaller value indicates better regulation performance.

---

## Importance of Line Regulation

An ideal regulator should maintain:

**V<sub>OUT</sub> = Constant**

even if the supply voltage varies.

Good line regulation ensures:

- Stable output voltage
- Reduced sensitivity to supply fluctuations
- Improved performance of analog circuits
- Reliable operation under battery discharge conditions

---

## Observation from Figure 11

The graph can be divided into two regions.

---

### Region 1: Dropout Region

For:

**V<sub>IN</sub> < 1.70 V**

the output voltage follows the input voltage.

<div align="center">

<table>
<tr>
<th>V<sub>IN</sub></th>
<th>V<sub>OUT</sub></th>
</tr>

<tr>
<td>1.60 V</td>
<td>1.60 V</td>
</tr>

<tr>
<td>1.70 V</td>
<td>1.70 V</td>
</tr>

</table>

</div>

In this region:

- The PMOS pass transistor is fully ON.
- The regulator has insufficient headroom.
- Closed-loop regulation is lost.

This is called the **dropout region**.

---

### Region 2: Regulation Region

Beyond approximately:

**V<sub>IN</sub> = 1.70 V**

the output becomes nearly constant.

Measured markers show:

#### Marker M76

**V<sub>IN</sub> = 1.75435 V**

**V<sub>OUT</sub> = 1.702446 V**

---

#### Marker M79

**V<sub>IN</sub> = 1.81589 V**

**V<sub>OUT</sub> = 1.702455 V**

The output changes only by a few microvolts despite a significant change in input voltage.

This confirms that the feedback loop is actively regulating the output.

---

## Line Regulation Calculation

Using the two marked points:

### Change in Output Voltage

**ΔV<sub>OUT</sub> = 1.702455 − 1.702446**

**ΔV<sub>OUT</sub> = 0.000009 V**

**ΔV<sub>OUT</sub> = 9 µV**

---

### Change in Input Voltage

**ΔV<sub>IN</sub> = 1.81589 − 1.75435**

**ΔV<sub>IN</sub> = 0.06154 V**

---

### Line Regulation

**Line Regulation = ΔV<sub>OUT</sub> / ΔV<sub>IN</sub>**

**Line Regulation = (9 × 10<sup>-6</sup>) / (0.06154)**

**Line Regulation = 1.462 × 10<sup>-4</sup> V/V**

Converting to mV/V:

**Line Regulation = 0.1462 mV/V**

or

**Line Regulation = 146.2 µV/V**

---

## Final Line Regulation Result

**Line Regulation = 0.146 mV/V**

or

**Line Regulation = 146.2 µV/V**

---

## Physical Interpretation

The result means that for every:

**1 V**

change in input voltage, the output voltage changes by only:

**146.2 µV**

which is extremely small.

### Example

If the input changes by:

**100 mV**

then:

**ΔV<sub>OUT</sub> = 0.1462 × 0.1**

**ΔV<sub>OUT</sub> = 14.6 µV**

Thus, almost all supply variations are rejected by the regulator.

---

## Why the Output Remains Constant

The excellent line regulation is achieved by:

### Error Amplifier

- Continuously compares **V<sub>ref</sub>** and **V<sub>fed</sub>**
- Detects even very small output changes

### PMOS Pass Transistor

- Adjusts its resistance automatically
- Compensates for supply variations

### Feedback Network

- Senses output voltage
- Forces:

**V<sub>fed</sub> = V<sub>ref</sub>**

### High Loop Gain

The approximately **80 dB** loop gain ensures very small regulation error.

---

## Relationship with Dropout Voltage

The graph also verifies the dropout point.

Regulation begins around:

**V<sub>IN</sub> ≈ 1.70 V**

while:

**V<sub>OUT</sub> ≈ 1.70 V**

Therefore:

**V<sub>DO</sub> = V<sub>IN</sub> − V<sub>OUT</sub>**

**V<sub>DO</sub> ≈ 95–100 mV**

which agrees closely with the dropout analysis obtained earlier.

---

## Performance Summary

<div align="center">

<table>
<tr>
<th>Parameter</th>
<th>Value</th>
</tr>

<tr>
<td>Input Voltage Range</td>
<td>1.6 V – 2.0 V</td>
</tr>

<tr>
<td>Regulated Output Voltage</td>
<td>≈ 1.702 V</td>
</tr>

<tr>
<td>Marker M76</td>
<td>(1.75435 V, 1.702446 V)</td>
</tr>

<tr>
<td>Marker M79</td>
<td>(1.81589 V, 1.702455 V)</td>
</tr>

<tr>
<td>Output Voltage Change</td>
<td>9 µV</td>
</tr>

<tr>
<td>Input Voltage Change</td>
<td>61.54 mV</td>
</tr>

<tr>
<td>Line Regulation</td>
<td>0.146 mV/V</td>
</tr>

<tr>
<td>Line Regulation</td>
<td>146.2 µV/V</td>
</tr>

<tr>
<td>Regulation Status</td>
<td>Excellent</td>
</tr>

<tr>
<td>Dropout Region</td>
<td>V<sub>IN</sub> &lt; 1.70 V</td>
</tr>

<tr>
<td>Regulated Region</td>
<td>V<sub>IN</sub> &gt; 1.70 V</td>
</tr>

</table>

</div>

---

## Conclusion

**Figure 11 illustrates the line regulation performance of the proposed CMOS LDO regulator. As the input voltage is swept from 1.6 V to 2.0 V, the output voltage remains nearly constant at approximately 1.702 V once the regulator enters the regulation region. Using the measured data points, the line regulation is calculated as 0.146 mV/V (146.2 µV/V), indicating excellent immunity to supply voltage variations. This demonstrates the effectiveness of the high-gain error amplifier, PMOS pass transistor, and feedback network in maintaining a stable regulated output voltage.**
