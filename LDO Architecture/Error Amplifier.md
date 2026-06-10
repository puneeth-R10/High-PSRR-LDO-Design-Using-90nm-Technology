## Error Amplifier ( PM0,PM1, PM2, NM0,NM1,NM2,NM3,NM4 ) 

### 1. NM0 and NM1 — Differential Input Pair

These are the main input transistors of the Error Amplifier (EA).

#### Connections

- Gate of NM0 → V<sub>ref</sub>
- Gate of NM1 → V<sub>fed</sub> (feedback voltage from the output divider)

#### Function

They compare:

**V<sub>err</sub> = V<sub>ref</sub> − V<sub>fed</sub>**

and convert this voltage difference into a current difference.

#### Case 1: Output Voltage Drops

When **V<sub>out</sub>** decreases:

**V<sub>fed</sub> < V<sub>ref</sub>**

Therefore:

**V<sub>GS,NM0</sub> > V<sub>GS,NM1</sub>**

**Result:**

- NM0 conducts more current
- NM1 conducts less current

The differential pair steers current toward NM0.

#### Case 2: Output Voltage Increases

When:

**V<sub>fed</sub> > V<sub>ref</sub>**

then:

**V<sub>GS,NM1</sub> > V<sub>GS,NM0</sub>**

**Result:**

- NM1 conducts more current
- NM0 conducts less current

Current is steered toward NM1.

#### Role

NM0 and NM1 perform the actual error-sensing operation.

---

### 2. PM0 and PM1 — Active Load / Current Mirror

These two PMOS transistors form the load of the differential pair.

#### PM0

PM0 is diode-connected:

**Gate = Drain**

This forces a current through PM0 and establishes a mirror reference.

#### PM1

PM1 mirrors the PM0 current.

Therefore:

**I<sub>PM1</sub> ≈ I<sub>PM0</sub>**

#### Why Use PM0–PM1?

Without PM0–PM1:

- Differential pair output remains differential.

With PM0–PM1:

- Differential current is converted to a single-ended output.

This greatly increases gain.

#### Result

The first-stage output node becomes:

**V<sub>X</sub>**

at the drain of NM1 / PM1.

This node drives the second gain stage.

---

### 3. NM2 — Bias Reference Transistor

NM2 receives the external bias current:

**I<sub>bias</sub>**

shown on the left side.

#### Function

NM2 is diode-connected.

It converts the bias current into a bias voltage:

**V<sub>GS,NM2</sub>**

This voltage is used to bias current mirrors.

#### Role

Generates a stable reference current for the EA.

---

### 4. NM3 — Tail Current Source

NM3 shares the same gate voltage as NM2.

Hence, NM2 and NM3 form an NMOS current mirror.

#### Current Relation

**I<sub>NM3</sub> = [(W/L)<sub>NM3</sub> / (W/L)<sub>NM2</sub>] × I<sub>bias</sub>**

#### Function

NM3 supplies the tail current for the differential pair:

**I<sub>tail</sub>**

This current is split between NM0 and NM1.

#### Why Important?

Provides:

- Constant bias current
- High gain
- Good CMRR
- Stable operating point

---

### 5. PM2 — Second Gain Stage Transistor

PM2 forms the second stage of the Error Amplifier (EA).

Its gate is driven by the first-stage output node.

#### Function

PM2 acts as a common-source amplifier.

Small voltage changes at its gate create large current changes.

Thus, it provides:

**A<sub>v2</sub>**

(second-stage voltage gain).

#### Why Needed?

The differential pair alone may provide:

**20–40 dB**

of gain.

An LDO usually requires:

**60–80 dB**

or more loop gain.

PM2 supplies the additional gain needed.

---

### 6. NM4 — Active Load / Current Sink for Second Stage

NM4 is biased from the same bias network as NM2 and NM3.

#### Function

NM4 acts as a constant current sink.

It provides:

**I<sub>bias2</sub>**

for PM2.

#### Why Needed?

PM2 and NM4 together form a high-gain common-source stage.

The gain is approximately:

**A<sub>v2</sub> = g<sub>m,PM2</sub>(r<sub>o,PM2</sub> ∥ r<sub>o,NM4</sub>)**

where:

- g<sub>m,PM2</sub> = transconductance of PM2
- r<sub>o,PM2</sub> = output resistance of PM2
- r<sub>o,NM4</sub> = output resistance of NM4

Large output resistance results in high voltage gain.
