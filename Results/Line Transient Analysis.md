# Line Transient Analysis 
<p align="center">
<img width="1600" height="900" alt="Image" src="https://github.com/user-attachments/assets/9018ba8c-422b-482a-9530-ad8d4d6fe749" />  
<br>
  <em>[Figure 13: Line Transient Analysis Plot ]</em>
</p>


Figure 13 shows the **line transient response** of the proposed CMOS LDO regulator. In this simulation, the input voltage (**V<sub>DD</sub>**) is intentionally changed from **1.7 V to 1.9 V** and then back to **1.7 V**, while observing the corresponding output voltage response (**V<sub>OUT</sub>**).

The purpose of this analysis is to evaluate how quickly and accurately the LDO maintains regulation when sudden supply voltage variations occur.

---

## What is Line Transient Response?

Line transient response measures the ability of an LDO to maintain a constant output voltage when the input supply voltage changes abruptly.

Mathematically:

**ΔV<sub>OUT</sub> = f(ΔV<sub>IN</sub>)**

An ideal LDO should maintain:

**V<sub>OUT</sub> = Constant**

even when:

**V<sub>IN</sub>**

changes suddenly.

---

## Input Voltage Variation

From the green waveform:

### Initial Condition

**V<sub>DD</sub> = 1.7 V**

until approximately:

**t = 1 µs**

---

### Rising Input Step

At:

**t = 1.09 µs**

the input voltage changes to:

**V<sub>DD</sub> = 1.9 V**

Input step magnitude:

**ΔV<sub>IN</sub> = 1.9 − 1.7**

**ΔV<sub>IN</sub> = 0.2 V**

### Final Result

**ΔV<sub>IN</sub> = 200 mV**

---

### Falling Input Step

At:

**t = 6.21 µs**

the supply returns to:

**V<sub>DD</sub> = 1.7 V**

---

## Output Voltage Response

The red waveform represents the regulated output voltage.

---

### Before Input Step

From the markers:

**V<sub>OUT</sub> = 1.6996 V**

at

**t = 550 ns**

The regulator is in steady-state operation.

---

## Response to Rising Input Step

When:

**V<sub>DD</sub> : 1.7 V → 1.9 V**

the output experiences a temporary overshoot.

Maximum output voltage:

**V<sub>OUT,peak</sub> = 1.807 V**

at approximately:

**t = 1.1 µs**

---

## Overshoot Calculation

**V<sub>overshoot</sub> = V<sub>OUT,peak</sub> − V<sub>OUT,steady</sub>**

**V<sub>overshoot</sub> = 1.807 − 1.6996**

**V<sub>overshoot</sub> = 0.1074 V**

**V<sub>overshoot</sub> = 107.4 mV**

---

### Percentage Overshoot

**%OS = (107.4 mV / 1.6996 V) × 100**

**%OS = 6.32 %**

---

## Settling Process

After the overshoot:

### Marker M25

**t = 1.576 µs**

**V<sub>OUT</sub> = 1.7202 V**

---

### Marker M26

**t = 1.969 µs**

**V<sub>OUT</sub> = 1.7092 V**

---

### Marker M27

**t = 2.422 µs**

**V<sub>OUT</sub> = 1.7084 V**

---

### Marker M28

**t = 4.84 µs**

**V<sub>OUT</sub> = 1.708 V**

The output settles to its final regulated value.

---

## Settling Time Calculation

Input step occurs at:

**t<sub>step</sub> = 1.09 µs**

Output settles around:

**t<sub>settled</sub> = 2.42 µs**

Therefore:

**t<sub>s</sub> = 2.42 − 1.09**

**t<sub>s</sub> = 1.33 µs**

### Settling Time

**t<sub>s</sub> ≈ 1.33 µs**

---

## Response to Falling Input Step

At:

**t = 6.21 µs**

the input voltage returns from:

**1.9 V → 1.7 V**

The output voltage remains close to:

**1.708 V**

with negligible disturbance.

This indicates strong feedback control and good supply rejection.

---

## Why Does Overshoot Occur?

When the input voltage suddenly increases:

**V<sub>IN</sub> ↑**

the PMOS pass transistor momentarily conducts more current.

The error amplifier cannot react instantaneously because of:

- Finite bandwidth
- Compensation capacitor (**C<sub>c</sub>**)
- Internal poles

As a result:

**V<sub>OUT</sub>**

briefly rises before the feedback loop corrects the error.

---

## Role of Individual Blocks During Line Transient

### Error Amplifier

- Detects output voltage increase
- Generates corrective gate voltage

---

### PMOS Pass Transistor (PM3)

- Initially passes excess current
- Subsequently reduces conduction

---

### Miller Compensation (R<sub>c</sub>–C<sub>c</sub>)

- Prevents oscillation
- Controls settling behavior
- Improves damping

---

### Output Capacitor (C<sub>out</sub>)

- Absorbs excess charge
- Reduces voltage spikes

---

### Feedback Network

- Continuously senses output voltage
- Forces:

**V<sub>fed</sub> = V<sub>ref</sub>**

after the transient.

---

## Line Transient Recovery Performance

The waveform demonstrates:

### Stability

No sustained oscillation is observed.

### Fast Recovery

**t<sub>s</sub> ≈ 1.33 µs**

### Controlled Overshoot

The output returns smoothly to its nominal value.

### Effective Regulation

Despite a **200 mV** supply variation, the output remains close to the regulated value after settling.

---

## Summary Table

<div align="center">

<table>
<tr>
<th>Parameter</th>
<th>Value</th>
</tr>

<tr>
<td>Initial Input Voltage</td>
<td>1.7 V</td>
</tr>

<tr>
<td>Final Input Voltage</td>
<td>1.9 V</td>
</tr>

<tr>
<td>Input Step Magnitude</td>
<td>200 mV</td>
</tr>

<tr>
<td>Initial Output Voltage</td>
<td>1.6996 V</td>
</tr>

<tr>
<td>Peak Output Voltage</td>
<td>1.807 V</td>
</tr>

<tr>
<td>Overshoot</td>
<td>107.4 mV</td>
</tr>

<tr>
<td>Percentage Overshoot</td>
<td>6.32 %</td>
</tr>

<tr>
<td>Final Regulated Output</td>
<td>1.708 V</td>
</tr>

<tr>
<td>Settling Time</td>
<td>≈ 1.33 µs</td>
</tr>

<tr>
<td>Oscillation</td>
<td>Not Observed</td>
</tr>

<tr>
<td>Stability</td>
<td>Stable</td>
</tr>

<tr>
<td>Regulation Quality</td>
<td>Good</td>
</tr>

</table>

</div>

---

## Conclusion

**Figure 13 presents the line transient response of the proposed CMOS LDO regulator. A 200 mV input voltage step from 1.7 V to 1.9 V causes a temporary output overshoot of approximately 107.4 mV. The feedback loop quickly corrects the disturbance, and the output settles to its regulated value of approximately 1.708 V within 1.33 µs. When the input voltage returns to 1.7 V, the regulator maintains stable operation with negligible disturbance. These results confirm that the proposed LDO exhibits good line transient performance, fast recovery, and stable closed-loop operation.**
