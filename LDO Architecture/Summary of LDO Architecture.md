## 1. Reference Voltage (V<sub>ref</sub>)

The reference voltage is the target voltage used by the regulator.

### Examples

- 0.6 V
- 1.0 V
- 1.2 V

### Characteristics

- Highly accurate
- Temperature independent
- Low noise

The reference determines the final output voltage.

---

## 2. Error Amplifier (EA)

The Error Amplifier (EA) is the **brain of the LDO**.

It continuously compares:

- **V<sub>ref</sub>**
- **V<sub>fed</sub>**

where **V<sub>fed</sub>** is the feedback voltage.

### Error Signal

**V<sub>error</sub> = V<sub>ref</sub> − V<sub>fed</sub>**

---

### First Gain Stage

#### NM0 and NM1

Differential input pair.

##### Inputs

- NM0 → V<sub>ref</sub>
- NM1 → V<sub>fed</sub>

##### Function

Compare V<sub>ref</sub> and V<sub>fed</sub>.

---

#### PM0 and PM1

Current mirror active load.

##### Functions

- Convert differential signal into a single-ended signal
- Increase gain

##### Output of First Stage

**Node X**

---

### Bias Network

#### NM2

Diode-connected bias transistor.

Receives:

**I<sub>bias</sub>**

Creates the bias voltage.

---

#### NM3

Current mirror transistor.

Provides tail current to the NM0-NM1 differential pair.

---

### Second Gain Stage

#### PM2

Common-source amplifier.

Provides additional gain.

---

#### NM4

Current sink load.

Works with PM2 to create a high-gain stage.

---

### Why Two Stages?

A single stage may provide:

**20–40 dB**

of gain.

An LDO typically requires:

**60–100 dB**

of loop gain.

Therefore, a second gain stage is required.

---

## 3. Miller Compensation (R<sub>c</sub> – C<sub>c</sub>)

Two-stage amplifiers are prone to instability.

To stabilize the EA:

- **C<sub>c</sub>** → Miller capacitor
- **R<sub>c</sub>** → Nulling resistor

---

### Function of C<sub>c</sub>

- Creates pole splitting
- Moves poles apart
- Produces a dominant pole
- Improves phase margin

---

### Function of R<sub>c</sub>

- Eliminates the Right-Half-Plane (RHP) zero
- Improves transient response
- Improves stability

---

## 4. Pass Transistor PM3

PM3 is the power device of the regulator.

It supplies load current from **V<sub>in</sub>** to **V<sub>out</sub>**.

### Function

Acts like a variable resistor.

The EA controls its gate voltage.

---

### If Output Drops

**V<sub>out</sub> ↓**

- EA increases PM3 conduction
- More current flows
- Output voltage recovers

---

### If Output Rises

**V<sub>out</sub> ↑**

- EA decreases PM3 conduction
- Less current flows
- Output voltage decreases

---

## 5. Feedback Network (R<sub>0</sub> and R<sub>1</sub>)

These resistors form a voltage divider.

```text
Vout
 |
R0
 |
Vfed
 |
R1
 |
GND
```

### Feedback Voltage

**V<sub>fed</sub> = V<sub>out</sub> × [R<sub>1</sub> / (R<sub>0</sub> + R<sub>1</sub>)]**

At regulation:

**V<sub>fed</sub> = V<sub>ref</sub>**

Therefore:

**V<sub>out</sub> = V<sub>ref</sub>(1 + R<sub>0</sub>/R<sub>1</sub>)**

Thus, R<sub>0</sub> and R<sub>1</sub> determine the output voltage.

---

## 6. Output Capacitor (C<sub>out</sub>)

The output capacitor acts as an energy reservoir.

### Functions

#### Energy Storage

**Q = CV**

Stores charge during sudden load changes.

---

#### Ripple Reduction

Smooths the output voltage.

---

#### Improves Transient Response

Supplies current before PM3 reacts.

---

#### Creates Output Pole

**f<sub>p</sub> = 1 / (2πR<sub>load</sub>C<sub>out</sub>)**

which affects stability.

---

## 7. ESR (Equivalent Series Resistance)

Real capacitors contain ESR.

### Model

```text
ESR
 |
Cout
 |
GND
```

---

### ESR Zero

ESR creates:

**f<sub>z</sub> = 1 / (2π × ESR × C<sub>out</sub>)**

This introduces phase lead.

### Benefits

- Improves phase margin
- Helps stabilize the loop

---

## 8. Load Current (I<sub>load</sub>)

Represents the current demanded by the load.

### Examples

- Processor
- Sensor
- ADC
- RF Circuit

The LDO continuously adjusts PM3 such that:

**I<sub>pass</sub> = I<sub>load</sub>**

---

## Complete Regulation Process

### Step 1

Load suddenly increases.

**I<sub>load</sub> ↑**

---

### Step 2

Output capacitor supplies current.

**V<sub>out</sub> ↓**

slightly.

---

### Step 3

Feedback voltage decreases.

**V<sub>fed</sub> ↓**

---

### Step 4

EA detects:

**V<sub>ref</sub> > V<sub>fed</sub>**

---

### Step 5

EA drives PM3 harder.

---

### Step 6

More current flows from **V<sub>in</sub>**.

---

### Step 7

Output returns to regulation.

**V<sub>fed</sub> = V<sub>ref</sub>**

---

## Overall LDO Control Loop

```text
Vref
  |
  v
Error Amplifier
  |
  v
Pass PMOS (PM3)
  |
  v
Vout
  |
  v
R0-R1 Divider
  |
  v
Vfed
  |
  +-----> Back to EA
```

This is a **negative feedback system**.

The loop continuously adjusts PM3 to maintain a constant output voltage.

---

<div align="center">

<h3>Summary Table</h3>

<table>
<tr>
<th>Block</th>
<th>Components</th>
<th>Function</th>
</tr>

<tr>
<td>Reference</td>
<td>V<sub>ref</sub></td>
<td>Provides accurate reference voltage</td>
</tr>

<tr>
<td>Differential Pair</td>
<td>NM0, NM1</td>
<td>Compares V<sub>ref</sub> and V<sub>fed</sub></td>
</tr>

<tr>
<td>Active Load</td>
<td>PM0, PM1</td>
<td>Current mirror, converts differential to single-ended output</td>
</tr>

<tr>
<td>Bias Circuit</td>
<td>NM2, NM3</td>
<td>Generates bias and tail current</td>
</tr>

<tr>
<td>Second Gain Stage</td>
<td>PM2, NM4</td>
<td>Provides additional gain</td>
</tr>

<tr>
<td>Compensation</td>
<td>R<sub>c</sub>, C<sub>c</sub></td>
<td>Stabilizes EA and improves phase margin</td>
</tr>

<tr>
<td>Pass Device</td>
<td>PM3</td>
<td>Controls current from V<sub>in</sub> to V<sub>out</sub></td>
</tr>

<tr>
<td>Feedback Network</td>
<td>R<sub>0</sub>, R<sub>1</sub></td>
<td>Senses output voltage and sets V<sub>out</sub></td>
</tr>

<tr>
<td>Output Capacitor</td>
<td>C<sub>out</sub></td>
<td>Stores charge and improves transient response</td>
</tr>

<tr>
<td>ESR</td>
<td>ESR of C<sub>out</sub></td>
<td>Creates ESR zero and improves stability</td>
</tr>

<tr>
<td>Load</td>
<td>I<sub>load</sub></td>
<td>Current demanded by the external circuit</td>
</tr>

<tr>
<td>Dominant Pole</td>
<td>Miller Compensation</td>
<td>Ensures stable loop operation</td>
</tr>

<tr>
<td>Regulation Condition</td>
<td>V<sub>fed</sub> = V<sub>ref</sub></td>
<td>Output voltage is correctly regulated</td>
</tr>

<tr>
<td>Output Voltage Equation</td>
<td>V<sub>out</sub> = V<sub>ref</sub>(1 + R<sub>0</sub>/R<sub>1</sub>)</td>
<td>Determines regulated output voltage</td>
</tr>

</table>

</div>
