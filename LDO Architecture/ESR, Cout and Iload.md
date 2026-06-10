## Output Capacitor (C<sub>out</sub>), ESR, and Load Current (I<sub>load</sub>)

### 1. Output Capacitor (C<sub>out</sub>)

#### What is C<sub>out</sub>?

**C<sub>out</sub>** is the capacitor connected between the LDO output and ground.

---

### Functions of C<sub>out</sub>

#### A) Charge Storage

The output capacitor stores electrical energy:

**Q = C × V**

When the load current suddenly increases, the capacitor supplies current immediately before the pass transistor can react.

```text
Load Current ↑ Suddenly

Cout Supplies Current First

Then EA Adjusts PM3
```

This helps maintain the output voltage during fast load transients.

---

#### B) Reduces Output Ripple

The output capacitor smooths voltage variations at the output.

Without **C<sub>out</sub>**:

- Large output ripple
- Poor transient response
- Increased noise

With **C<sub>out</sub>**:

- Stable output voltage
- Reduced ripple
- Improved noise performance

---

#### C) Creates the Output Pole

The output capacitor introduces an output pole:

**f<sub>p,out</sub> = 1 / [2πR<sub>load</sub>C<sub>out</sub>]**

This pole significantly affects the stability of the LDO.

---

### 2. ESR (Equivalent Series Resistance)

#### What is ESR?

A real capacitor is not ideal.

Its practical model is:

```text
      ESR
       |
       |
     Cout
       |
      GND
```

**ESR (Equivalent Series Resistance)** is the small internal resistance of the capacitor.

Typical values:

- Ceramic capacitor → Very low ESR
- Electrolytic capacitor → Higher ESR

---

### Why ESR is Important

ESR introduces a zero into the loop transfer function:

**f<sub>z,ESR</sub> = 1 / [2π × ESR × C<sub>out</sub>]**

This is known as the **ESR Zero**.

---

### Benefit of the ESR Zero

The output pole introduces phase lag:

```text
Output Pole → −90°
```

The ESR zero introduces phase lead:

```text
ESR Zero → +90°
```

Therefore, the ESR zero can improve phase margin and enhance stability.

---

### Example

Suppose:

- **C<sub>out</sub> = 10 μF**
- **ESR = 0.1 Ω**

Then:

**f<sub>z,ESR</sub> = 1 / [2π(0.1)(10 μF)]**

Therefore:

**f<sub>z,ESR</sub> ≈ 159 kHz**

This zero can help stabilize the LDO control loop.

---

### Too Much ESR

If ESR becomes too large:

- Larger voltage drop
- Increased ripple
- Poorer load regulation
- Reduced efficiency

Therefore, ESR must be carefully selected.

---

### 3. Load Current (I<sub>load</sub>)

#### What is I<sub>load</sub>?

**I<sub>load</sub>** represents the current drawn by the external circuit powered by the LDO.

Examples include:

- Microcontrollers (MCUs)
- ADCs
- DACs
- RF blocks
- Sensors
- Digital logic circuits

---

### Relationship with Output Voltage

At steady state:

**I<sub>pass</sub> = I<sub>load</sub>**

The pass transistor supplies exactly the current demanded by the load.

---

### When Load Current Increases

Suppose:

**I<sub>load</sub> ↑**

Initially:

- Output capacitor discharges
- **V<sub>out</sub> ↓**

Then:

- **V<sub>fed</sub> ↓**
- Error amplifier detects the error
- PM3 turns ON harder
- More current is supplied from **V<sub>in</sub>**

Finally:

- Output voltage returns to regulation

---

### When Load Current Decreases

Suppose:

**I<sub>load</sub> ↓**

Initially:

- Excess current charges **C<sub>out</sub>**
- **V<sub>out</sub> ↑**

Then:

- **V<sub>fed</sub> ↑**
- Error amplifier reduces PM3 conduction

Finally:

- Output voltage settles back to its regulated value

This is another example of negative feedback action.

---

### Combined Operation During a Load Transient

Assume:

**I<sub>load</sub> : 10 mA → 100 mA**

#### Immediately After the Load Step

The error amplifier cannot react instantaneously.

Therefore:

**I<sub>Cout</sub> = 90 mA**

is temporarily supplied by the output capacitor.

As a result:

- Output voltage droops slightly
- The capacitor provides the missing current

---

#### After a Short Time

The error amplifier detects:

**V<sub>out</sub> ↓**

The EA then drives PM3 harder.

Consequently:

- More current is delivered from **V<sub>in</sub>**
- The load current demand is met

---

#### Final Steady-State Condition

**I<sub>pass</sub> = 100 mA**

**I<sub>Cout</sub> = 0**

The pass transistor now supplies the entire load current and the output voltage returns to its nominal regulated value.



