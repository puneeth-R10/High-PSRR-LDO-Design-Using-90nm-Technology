## Feedback Network (R<sub>0</sub> and R<sub>1</sub>)

### 1. Purpose of the Feedback Network

The error amplifier (EA) cannot directly compare a large output voltage (e.g., 1.8 V or 3.3 V) with a small reference voltage.

Therefore, the output voltage is scaled down using the feedback resistor divider:

**V<sub>fed</sub> = V<sub>out</sub> × [R<sub>1</sub> / (R<sub>0</sub> + R<sub>1</sub>)]**

The EA compares:

- **V<sub>ref</sub>**
- **V<sub>fed</sub>**

and adjusts the pass transistor (**PM3**) accordingly.

---

### 2. How Regulation Occurs

At steady state:

**V<sub>fed</sub> = V<sub>ref</sub>**

Substituting the divider equation:

**V<sub>ref</sub> = V<sub>out</sub> × [R<sub>1</sub> / (R<sub>0</sub> + R<sub>1</sub>)]**

Therefore:

**V<sub>out</sub> = V<sub>ref</sub>(1 + R<sub>0</sub>/R<sub>1</sub>)**

This is the fundamental LDO output voltage equation.

---

### 3. If Output Voltage Falls

Suppose:

**V<sub>out</sub> ↓** Then: **V<sub>fed</sub> ↓**

Now:

**V<sub>ref</sub> > V<sub>fed</sub>**

The EA detects a positive error and drives PM3 harder.

#### Result

- More current flows from **V<sub>in</sub>** to **V<sub>out</sub>**
- Output voltage rises back to its regulated value

---

### 4. If Output Voltage Rises

Suppose:

**V<sub>out</sub> ↑** Then: **V<sub>fed</sub> ↑**

Now:

**V<sub>fed</sub> > V<sub>ref</sub>**

The EA reduces PM3 conduction.

#### Result

- Less current is supplied to the load
- Output voltage falls back to its regulated value

This creates **negative feedback**, which stabilizes the output voltage.

---

### 5. Selecting R<sub>0</sub> and R<sub>1</sub>

From:

**V<sub>out</sub> = V<sub>ref</sub>(1 + R<sub>0</sub>/R<sub>1</sub>)**

For example, if:

- **V<sub>ref</sub> = 1.2 V**
- Desired **V<sub>out</sub> = 3.3 V**

Then:

**R<sub>0</sub>/R<sub>1</sub> = (3.3/1.2) − 1 = 1.75**

Choose:

- **R<sub>1</sub> = 100 kΩ**
- **R<sub>0</sub> = 175 kΩ**

which gives approximately:

**V<sub>out</sub> ≈ 3.3 V**

---

### 6. Why Large Resistance Values Are Used

The feedback divider continuously draws current:

**I<sub>FB</sub> = V<sub>out</sub> / (R<sub>0</sub> + R<sub>1</sub>)**

This current represents wasted power.

Therefore, large resistor values are commonly used, such as:

- 100 kΩ
- 200 kΩ
- 500 kΩ
- 1 MΩ

to minimize quiescent current and improve power efficiency.

#### Benefit

Larger resistor values result in:

- Lower feedback current (**I<sub>FB</sub>**)
- Lower power consumption
- Better battery life in portable applications
