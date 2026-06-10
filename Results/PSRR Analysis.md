# Power Supply Rejection Ratio (PSRR)

<p align="center">
<img width="1101" height="703" alt="Image" src="https://github.com/user-attachments/assets/802b5440-2183-48c9-91e3-b32b6cc25c97" />
  <br>
  <em>[Figure 9: PSRR Plot ]</em>
</p>


Figure 9 shows the **Power Supply Rejection Ratio (PSRR)** response of the designed CMOS LDO regulator obtained from AC analysis in Cadence Virtuoso. PSRR is one of the most important performance parameters of an LDO because it indicates how effectively the regulator suppresses noise and ripple present on the input supply before it reaches the regulated output.

---

## What is PSRR?

Power Supply Rejection Ratio (PSRR) measures the ability of an LDO to reject disturbances appearing at the input supply.

Mathematically:

**PSRR(dB) = 20log<sub>10</sub>(V<sub>out(ac)</sub> / V<sub>in(ac)</sub>)**

Many texts express PSRR as:

**PSRR(dB) = 20log<sub>10</sub>(V<sub>in(ac)</sub> / V<sub>out(ac)</sub>)**

Since Cadence plots transfer gain, the curve appears as a negative value. A more negative value indicates better supply-noise rejection.

---

## Importance of PSRR

A high PSRR ensures that:

- Supply noise does not appear at the output.
- Analog circuits receive a clean DC voltage.
- ADCs, DACs, PLLs, RF circuits, and sensors operate accurately.
- Switching noise from DC-DC converters is attenuated.

For example, if a **100 mV** ripple exists at the input and the PSRR is **80 dB**:

**V<sub>out(noise)</sub> = 100 mV × 10<sup>-80/20</sup>**

**V<sub>out(noise)</sub> = 10 µV**

Thus, most of the supply noise is removed.

---

## Observations from Figure 9

The PSRR response is plotted from approximately:

**1 Hz → 10 GHz**

The graph shows that the LDO exhibits excellent low-frequency supply rejection and gradually loses rejection capability as frequency increases.

---

## Region 1: Low-Frequency PSRR

### At 10 kHz

**PSRR ≈ -80.76 dB**

### At 100 kHz

**PSRR ≈ -80.29 dB**

The curve remains almost flat around:

**-80 dB**

through the low-frequency range.

### Explanation

At low frequencies:

- The error amplifier has very high gain.
- Negative feedback is strong.
- The pass transistor actively suppresses supply variations.

As a result, very little input ripple reaches the output.

This demonstrates excellent low-frequency rejection performance.

---

## Region 2: Mid-Frequency PSRR

Between approximately:

**100 kHz → 10 MHz**

the PSRR begins to degrade gradually.

### At 1 MHz

**PSRR ≈ -78.39 dB**

Although the rejection decreases slightly, it remains very good.

### Reason

As frequency increases:

- Error amplifier gain decreases.
- Loop gain starts to roll off.
- Feedback becomes less effective.

Therefore, supply-noise suppression gradually reduces.

---

## Region 3: High-Frequency PSRR

Above approximately:

**10 MHz**

the PSRR decreases rapidly.

The curve rises toward:

**-20 dB**

at very high frequencies.

### Reason

At high frequencies:

- The error amplifier can no longer respond.
- Loop gain becomes very small.
- The pass transistor gate cannot react quickly enough.
- Parasitic capacitances dominate the response.

Consequently, some input noise directly couples to the output.

---

## Role of Each Block in PSRR Improvement

### Error Amplifier

The two-stage error amplifier:

- Detects supply-induced output variations.
- Corrects output voltage errors.
- Provides high DC gain.

High gain directly improves low-frequency PSRR.

---

### Miller Compensation (R<sub>c</sub>–C<sub>c</sub>)

The compensation network:

- Stabilizes the loop.
- Maintains sufficient phase margin.
- Extends effective feedback action.

This improves PSRR in the low- and mid-frequency regions.

---

### PMOS Pass Transistor (PM3)

The PMOS pass transistor provides isolation between:

**V<sub>DD</sub>** and **V<sub>OUT</sub>**

Because the gate is actively controlled by the error amplifier, input disturbances are attenuated before reaching the output.

---

### Output Capacitor (C<sub>out</sub>)

The output capacitor acts as a low-pass filter.

It:

- Absorbs high-frequency noise.
- Reduces output ripple.
- Improves high-frequency PSRR.

---

### ESR Zero

The ESR of the output capacitor introduces a zero that contributes phase lead and helps maintain loop stability, indirectly supporting PSRR performance.

---

## Interpretation of Measured Results

<div align="center">

<table>
<tr>
<th>Frequency</th>
<th>PSRR</th>
</tr>

<tr>
<td>10 kHz</td>
<td>-80.76 dB</td>
</tr>

<tr>
<td>100 kHz</td>
<td>-80.29 dB</td>
</tr>

<tr>
<td>1 MHz</td>
<td>-78.39 dB</td>
</tr>

</table>

</div>

These values indicate that the proposed LDO provides approximately **80 dB supply-noise rejection** over a wide frequency range, which is considered excellent for low-power CMOS LDO regulators.

---

## Practical Meaning of 80 dB PSRR

For:

**PSRR = 80 dB**

the output ripple is:

**10<sup>-80/20</sup> = 10<sup>-4</sup>**

times the input ripple.

Therefore:

<div align="center">

<table>
<tr>
<th>Input Ripple</th>
<th>Output Ripple</th>
</tr>

<tr>
<td>100 mV</td>
<td>10 µV</td>
</tr>

<tr>
<td>10 mV</td>
<td>1 µV</td>
</tr>

<tr>
<td>1 mV</td>
<td>100 nV</td>
</tr>

</table>

</div>

This demonstrates the strong filtering capability of the regulator.


