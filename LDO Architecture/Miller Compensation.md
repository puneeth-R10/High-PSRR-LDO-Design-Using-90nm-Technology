## Miller Compensation in the LDO Error Amplifier

In this LDO Error Amplifier (EA), the **R<sub>c</sub>–C<sub>c</sub>** network connected between the output of the first stage and the output of the second stage forms the **Miller compensation network**.

```text
First-Stage Output (Node X)
          |
         Rc
          |
         Cc
          |
Second-Stage Output (Node Y)
```

where:

- **C<sub>c</sub>** = Miller compensation capacitor
- **R<sub>c</sub>** = Nulling resistor (series resistor)

---

### Why Compensation is Needed

The Error Amplifier is a **two-stage amplifier**.

#### Stage 1

- NM0, NM1 : Differential input pair
- PM0, PM1 : Active load

#### Stage 2

- PM2 : Common-source amplifier
- NM4 : Current sink

Each stage creates a high-impedance node.

Therefore, the amplifier naturally contains two poles:

- **p<sub>1</sub>** at the first-stage output
- **p<sub>2</sub>** at the second-stage output

Without compensation:

- Pole **p<sub>1</sub>** introduces approximately 90° phase shift
- Pole **p<sub>2</sub>** introduces another 90° phase shift

Total phase shift can approach:

**180°**

while the loop gain is still greater than unity.

#### Result

 Oscillation

 Ringing

 Unstable LDO

---

### What the Miller Capacitor Does

The capacitor **C<sub>c</sub>** is connected between the input and output of the second gain stage.

This creates the **Miller Effect**.

The effective capacitance seen at the first-stage output becomes:

**C<sub>eq</sub> = C<sub>c</sub>(1 + A<sub>v2</sub>)**

where:

- **A<sub>v2</sub>** = gain of the second stage

Because **A<sub>v2</sub>** is large, a small capacitor behaves like a much larger capacitor.

---

### Pole Splitting

Miller compensation separates the poles.

#### Dominant Pole

Moves to a very low frequency:

**p<sub>1</sub> → very low frequency**

#### Non-Dominant Pole

Moves to a much higher frequency:

**p<sub>2</sub> → high frequency**

This phenomenon is called **Pole Splitting**.

#### Without Compensation

```text
p1      p2
|-------|
```

#### With Compensation

```text
p1---------------------p2
|                       |

```

Now only one pole is active near the unity-gain frequency.

#### Result

 Better phase margin

 Stable operation
 
 Improved loop stability

---

### Why R<sub>c</sub> is Added

If only **C<sub>c</sub>** is used, a **Right-Half-Plane (RHP) Zero** appears.

The RHP zero frequency is approximately:

**ω<sub>z,RHP</sub> = g<sub>m2</sub> / C<sub>c</sub>**

where:

- **g<sub>m2</sub>** = transconductance of PM2

---

### Problem with the RHP Zero

An RHP zero introduces:

- Gain increase
- Additional phase lag

This reduces overall stability.

#### Result

 Lower phase margin

 Greater tendency to oscillate

---

### Function of R<sub>c</sub> (Nulling Resistor)

Adding **R<sub>c</sub>** in series with **C<sub>c</sub>** shifts the zero location.

A proper choice is:

**R<sub>c</sub> ≈ 1 / g<sub>m2</sub>**

This moves the zero from the **Right-Half Plane (RHP)** to the **Left-Half Plane (LHP)**.

The resulting LHP zero can help compensate for the phase loss caused by the second pole.

#### Result

 Higher phase margin

 Faster settling time

 Better transient response

 Improved stability
