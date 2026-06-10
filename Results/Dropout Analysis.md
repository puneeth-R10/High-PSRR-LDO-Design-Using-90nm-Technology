# Dropout

<p align="center">
 <img width="1109" height="675" alt="Image" src="https://github.com/user-attachments/assets/31b457cf-3944-4a5b-8e51-cfc8d1728944" />
  <br>
  <em>[Figure 8: Dropout simulation result ]</em>
</p>

Figure 8 shows the transient simulation waveform used to determine the dropout performance of the designed LDO regulator.

From the waveform:

- **Input Voltage (V<sub>DD</sub>) = 1.8 V** (Red Trace)
- **Output Voltage (V<sub>OUT</sub>) ≈ 1.7041 V** (Green Trace)

The waveform indicates that after startup, the output voltage quickly settles and remains constant throughout the simulation period, demonstrating stable regulation.

---

## What is Dropout Voltage?

The dropout voltage of an LDO is the minimum voltage difference required between the input and output terminals for proper regulation.

Mathematically:

**V<sub>DO</sub> = V<sub>IN</sub> − V<sub>OUT</sub>**

where:

- **V<sub>DO</sub>** = Dropout Voltage
- **V<sub>IN</sub>** = Input Supply Voltage
- **V<sub>OUT</sub>** = Regulated Output Voltage

An LDO is said to be in regulation as long as:

**V<sub>IN</sub> > V<sub>OUT</sub> + V<sub>DO</sub>**

---

## Values Obtained from Figure 8

### Input Voltage

From the red waveform:

**V<sub>IN</sub> = 1.8 V**

### Output Voltage

From the marker on the green waveform:

**V<sub>OUT</sub> = 1.7041 V**

---

## Dropout Voltage Calculation

Using:

**V<sub>DO</sub> = V<sub>IN</sub> − V<sub>OUT</sub>**

Substituting the measured values:

**V<sub>DO</sub> = 1.8 − 1.7041**

**V<sub>DO</sub> = 0.0959 V**

**V<sub>DO</sub> = 95.9 mV**

---

## Final Result

**V<sub>DO</sub> = 95.9 mV**

or approximately:

**V<sub>DO</sub> ≈ 96 mV**

---

## Interpretation of the Result

A dropout voltage of approximately **96 mV** indicates that the regulator can maintain the desired output voltage even when the input voltage is only slightly higher than the output voltage.

This demonstrates:

- Low dropout operation
- Efficient voltage regulation
- Reduced power dissipation
- Suitability for battery-powered applications

Since the pass element is a **PMOS transistor operating in the linear region**, only a small voltage drop is required across the device to deliver the required load current.

---

## Power Loss Across the LDO

The voltage lost across the pass transistor is approximately equal to the dropout voltage.

The power dissipated across the pass device is:

**P<sub>loss</sub> = (V<sub>IN</sub> − V<sub>OUT</sub>) × I<sub>LOAD</sub>**

Using the calculated dropout voltage:

**P<sub>loss</sub> = (95.9 mV) × I<sub>LOAD</sub>**

Thus, a lower dropout voltage directly translates to:

- Lower power dissipation
- Higher power efficiency
- Longer battery life in portable systems

---

## Observation from the Waveform

The output voltage reaches its steady-state value at approximately:

**t ≈ 31 ms**

and remains nearly constant throughout the simulation interval.

No noticeable:

- Oscillations
- Overshoot
- Instability

are observed.

This indicates:

- Proper Miller compensation
- Adequate phase margin
- Stable closed-loop operation

The regulated output voltage remains around:

**V<sub>OUT</sub> ≈ 1.704 V**

while the supply voltage remains fixed at:

**V<sub>IN</sub> = 1.8 V**

resulting in a measured dropout voltage of approximately:

**V<sub>DO</sub> ≈ 96 mV**

---

### Conclusion

The transient simulation confirms that the proposed CMOS LDO regulator achieves a **low dropout voltage of approximately 96 mV** while maintaining stable output regulation. The absence of oscillations and the rapid settling behavior demonstrate the effectiveness of the two-stage error amplifier, Miller compensation network, and PMOS pass transistor in providing efficient and reliable voltage regulation.
