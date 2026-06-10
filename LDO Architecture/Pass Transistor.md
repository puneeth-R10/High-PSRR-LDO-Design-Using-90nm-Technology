## Types of Pass Transistor

<p align="center">
 <img width="523" height="353" alt="Image" src="https://github.com/user-attachments/assets/7cfbe544-bb8f-42fa-90f3-27e6faec521a" />
  <br>
  <em>[Figure 6: Analog LDO with Mn]</em>
</p>

We need to select the type of pass transistor between **P-type (MP)** and **N-type (MN)** for the desired purpose. **MP** has smaller dropout voltage (**V<sub>DO</sub>**), lower power supply rejection ratio (**PSRR**), and lower output pole frequency (**ω<sub>P,OUT</sub>**) than the N-type pass transistor (**MN**). The comparison of pass transistor types is shown in Table 1.

---
### Dropout Voltage (V<sub>DO</sub>)

**V<sub>DO</sub>** is the dropout voltage between **V<sub>IN</sub>** and **V<sub>OUT</sub>**. As shown in Figure 6, for **MN** operating in the saturation region, **V<sub>DO</sub>** should be large. Otherwise, **V<sub>G</sub>** should be larger than **V<sub>IN</sub>**, because **V<sub>G</sub>** should be larger than the sum of **V<sub>OUT</sub>** and the threshold voltage (**V<sub>th</sub>**) of **MN**.

---
**V<sub>G</sub> > V<sub>OUT</sub> + V<sub>th</sub>**

For example, if **V<sub>th</sub>** of **MN** is over **300 mV** and the specification requires **V<sub>DO</sub> < 200 mV**, a charge pump is needed to increase **V<sub>G</sub>** such that:

**V<sub>G</sub> > V<sub>IN</sub> + 100 mV**

---
### Power Supply Rejection Ratio (PSRR)

**PSRR** is the ratio of the change in **V<sub>IN</sub>** to the change in **V<sub>OUT</sub>** it produces.

If **V<sub>IN</sub>** fluctuates, in the **MN** case, **V<sub>OUT</sub>** is robust to **V<sub>IN</sub>** fluctuations since, from the perspective of **V<sub>OUT</sub>**, only the drain of **MN** fluctuates and the MOSFET is inherently robust to changes in **V<sub>DS</sub>**. However, in the **MP** case, the fluctuation is amplified by the PMOS gain (**A<sub>MP</sub>**) and delivered to **V<sub>OUT</sub>** because the variation occurs in **V<sub>GS</sub>**.

Thus, **MN-type LDOs generally exhibit higher PSRR than MP-type LDOs**. However, this is only a general tendency, and if a deeper analysis is conducted, the conclusion may become ambiguous. In brief, after determining the pass transistor type, the error amplifier (**EA**) architecture should be selected appropriately so that **v<sub>R</sub>** cannot be directly represented in **V<sub>OUT</sub>**.

---
### Pole Characteristics

The general structure of an LDO contains two low-frequency poles:

- **ω<sub>P,OUT</sub>** : Pole at the output node (**V<sub>OUT</sub>**)
- **ω<sub>P,G</sub>** : Pole at the gate node (**V<sub>G</sub>**)

---
#### NMOS Pass Transistor (MN)

In the **MN** case, since the low **1/g<sub>m</sub>** impedance of **MN** is seen by **V<sub>OUT</sub>**, **ω<sub>P,OUT</sub>** can easily be higher than **ω<sub>P,G</sub>**, making the LDO **Gate-Pole-Dominant (GPD)**.

---
#### PMOS Pass Transistor (MP)

In the **MP** case, since the high **r<sub>o</sub>** impedance of **MP** is seen by **V<sub>OUT</sub>**, it can become negligible. Therefore, depending on the load impedance, the LDO can operate as either:

- **Gate-Pole-Dominant (GPD)**
- **Output-Pole-Dominant (OPD)**

<p align="center">
<b>Table 1: Comparison between MP and MN</b>
</p>

<table align="center">
<tr>
<th>Pass Transistor Type</th>
<th>P-type (M<sub>P</sub>)</th>
<th>N-type (M<sub>N</sub>)</th>
</tr>

<tr>
<td>V<sub>DO</sub></td>
<td>Low</td>
<td>High</td>
</tr>

<tr>
<td>PSRR</td>
<td>Low</td>
<td>High</td>
</tr>

<tr>
<td>ω<sub>P,OUT</sub></td>
<td>Depends on I<sub>L</sub></td>
<td>High</td>
</tr>
</table>
