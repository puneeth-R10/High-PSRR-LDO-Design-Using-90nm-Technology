# Load Transient Analysis
<p align="center">
<img width="1600" height="900" alt="Image" src="https://github.com/user-attachments/assets/aee7bc57-ba5b-4324-9cd9-4438f0821c5d" />  <br>
  <em>[Figure 14:Load Transient Analysis Plot ]</em>
</p>

Figure 14 shows the **load transient response** of the proposed CMOS LDO regulator. In this analysis, the load current is abruptly changed while keeping the input voltage constant. The objective is to evaluate the regulator's ability to maintain a stable output voltage during sudden changes in load demand.

Load transient analysis is one of the most important tests for an LDO because practical loads such as microprocessors, ADCs, sensors, and communication circuits frequently switch between different current levels.

---

## What is Load Transient Response?

Load transient response measures the variation in output voltage when the load current changes suddenly.

Mathematically:

**ΔV<sub>OUT</sub> = f(ΔI<sub>LOAD</sub>)**

An ideal regulator should maintain:

**V<sub>OUT</sub> = Constant**

for any change in load current.

---

## Importance of Load Transient Analysis

Load transient performance determines:

- Voltage stability under dynamic loads
- Recovery speed
- Output voltage droop and overshoot
- Suitability for digital and mixed-signal systems

A good LDO should exhibit:

- Small undershoot
- Small overshoot
- Fast settling time
- No oscillation

---

## Observations from Figure 14

The waveform shows the output voltage response to a load current step.

The output voltage remains regulated around:

**1.702 V**

throughout the simulation.

The transient consists of two events.

### Event 1

At approximately:

**t = 1.0 µs**

the output voltage drops.

This indicates a sudden increase in load current.

---

### Event 2

At approximately:

**t = 6.1 µs**

the output voltage rises.

This indicates a sudden decrease in load current.

---

## Event 1: Load Current Increase

From the markers:

### Before Load Step

Marker M2:

**t = 1.0 µs**

**V<sub>OUT</sub> = 1.7026 V**

---

### Minimum Output Voltage

Marker M1:

**t = 1.11 µs**

**V<sub>OUT</sub> = 1.7021 V**

---

## Undershoot Calculation

**V<sub>undershoot</sub> = V<sub>initial</sub> − V<sub>minimum</sub>**

**V<sub>undershoot</sub> = 1.7026 − 1.7021**

**V<sub>undershoot</sub> = 0.0005 V**

**V<sub>undershoot</sub> = 0.5 mV**

---

### Percentage Undershoot

**%US = (0.5 mV / 1.7026 V) × 100**

**%US = 0.029 %**

---

## Physical Explanation

When the load current suddenly increases:

**I<sub>LOAD</sub> ↑**

the load demands more current than PM3 can immediately supply.

Initially:

- The output capacitor (**C<sub>OUT</sub>**) supplies the extra current.
- Stored charge is removed from the capacitor.

Therefore:

**V<sub>OUT</sub>**

drops temporarily.

The error amplifier detects:

**V<sub>fed</sub> < V<sub>ref</sub>**

and drives PM3 harder.

Additional current is then supplied to the load.

---

## Recovery After Load Increase

After the voltage dip:

### Minimum Point

**V<sub>OUT</sub> = 1.7021 V**

at

**t = 1.11 µs**

---

### Recovery Region

The output gradually returns toward regulation.

The recovery is smooth and free from oscillation.

This demonstrates:

- Adequate loop bandwidth
- Good phase margin
- Proper Miller compensation

---

## Event 2: Load Current Decrease

At approximately:

**t = 6.1 µs**

the load current decreases.

From the markers:

### Before Transition

Marker M4:

**V<sub>OUT</sub> = 1.7022 V**

at

**t = 6.10 µs**

---

### Peak Output Voltage

Marker M5:

**V<sub>OUT</sub> = 1.7027 V**

at

**t = 6.21 µs**

---

## Overshoot Calculation

**V<sub>overshoot</sub> = 1.7027 − 1.7022**

**V<sub>overshoot</sub> = 0.0005 V**

**V<sub>overshoot</sub> = 0.5 mV**

---

### Percentage Overshoot

**%OS = (0.5 mV / 1.7022 V) × 100**

**%OS = 0.029 %**

---

## Physical Explanation

When the load current suddenly decreases:

**I<sub>LOAD</sub> ↓**

the pass transistor PM3 continues supplying the previous current momentarily.

The excess current charges the output capacitor.

Consequently:

**V<sub>OUT</sub>**

rises slightly.

The error amplifier senses:

**V<sub>fed</sub> > V<sub>ref</sub>**

and reduces PM3 conduction.

The output voltage then returns to regulation.

---

## Settling Time Estimation

### Load Increase Event

Disturbance starts:

**t<sub>1</sub> = 1.0 µs**

Minimum voltage:

**t<sub>2</sub> = 1.11 µs**

Output substantially settles by approximately:

**t<sub>3</sub> ≈ 3.0 µs**

Therefore:

**t<sub>s</sub> = 3.0 − 1.0**

**t<sub>s</sub> = 2.0 µs**

---

### Load Decrease Event

Disturbance starts:

**t<sub>4</sub> = 6.10 µs**

Peak voltage:

**t<sub>5</sub> = 6.21 µs**

Output settles shortly after.

Estimated settling time:

**t<sub>s</sub> ≈ 1–2 µs**

---

## Role of Individual Blocks During Load Transient

### Output Capacitor (C<sub>OUT</sub>)

Provides immediate transient current:

**I<sub>C</sub> = C(dV/dt)**

and minimizes voltage droop.

---

### Error Amplifier

- Detects output voltage deviations
- Generates correction signal

---

### PMOS Pass Transistor (PM3)

Adjusts current supplied from:

**V<sub>IN</sub> → V<sub>OUT</sub>**

according to load demand.

---

### Feedback Network

Continuously senses output voltage and maintains:

**V<sub>fed</sub> = V<sub>ref</sub>**

---

### Miller Compensation (R<sub>c</sub>–C<sub>c</sub>)

Prevents oscillation during transient events and improves damping.

---

## Performance Evaluation

<div align="center">

<table>
<tr>
<th>Parameter</th>
<th>Desired</th>
</tr>

<tr>
<td>Overshoot</td>
<td>&lt; 10 mV</td>
</tr>

<tr>
<td>Undershoot</td>
<td>&lt; 10 mV</td>
</tr>

<tr>
<td>Settling Time</td>
<td>Few µs</td>
</tr>

<tr>
<td>Oscillation</td>
<td>None</td>
</tr>

</table>

</div>

### Obtained Results

<div align="center">

<table>
<tr>
<th>Parameter</th>
<th>Measured</th>
</tr>

<tr>
<td>Undershoot</td>
<td>0.5 mV</td>
</tr>

<tr>
<td>Overshoot</td>
<td>0.5 mV</td>
</tr>

<tr>
<td>Settling Time</td>
<td>≈ 1–2 µs</td>
</tr>

<tr>
<td>Oscillation</td>
<td>Not Observed</td>
</tr>

</table>

</div>

The obtained transient deviations are extremely small, indicating excellent dynamic regulation.

---

## Summary Table

<div align="center">

<table>
<tr>
<th>Parameter</th>
<th>Value</th>
</tr>

<tr>
<td>Nominal Output Voltage</td>
<td>1.7026 V</td>
</tr>

<tr>
<td>Minimum Output Voltage</td>
<td>1.7021 V</td>
</tr>

<tr>
<td>Peak Output Voltage</td>
<td>1.7027 V</td>
</tr>

<tr>
<td>Undershoot</td>
<td>0.5 mV</td>
</tr>

<tr>
<td>Overshoot</td>
<td>0.5 mV</td>
</tr>

<tr>
<td>Percentage Undershoot</td>
<td>0.029 %</td>
</tr>

<tr>
<td>Percentage Overshoot</td>
<td>0.029 %</td>
</tr>

<tr>
<td>Estimated Settling Time</td>
<td>1–2 µs</td>
</tr>

<tr>
<td>Stability</td>
<td>Stable</td>
</tr>

<tr>
<td>Oscillation</td>
<td>Not Observed</td>
</tr>

<tr>
<td>Regulation Performance</td>
<td>Excellent</td>
</tr>

</table>

</div>

---

## Conclusion

**Figure 14 illustrates the load transient response of the proposed CMOS LDO regulator. When the load current increases, the output voltage experiences a small undershoot of approximately 0.5 mV, while a load current decrease causes an overshoot of approximately 0.5 mV. In both cases, the output quickly returns to its regulated value within a few microseconds without oscillation. These results demonstrate that the proposed LDO possesses excellent load transient performance, fast recovery, strong stability, and effective regulation under dynamic load conditions.**
