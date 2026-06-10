# Working of CMOS LDO Regulator

<p align="center">
 <img width="916" height="652" alt="Image" src="https://github.com/user-attachments/assets/0f483f51-768c-4d98-910a-93b93ba7e53d" />
  <br>
  <em>[Figure 5: Expansion of Block Diagram of proposed LDO ]</em>
</p>


## I. Error amplifier

### Function:

The error amplifier acts as the brain of the LDO. It constantly checks whether the output voltage is at the desired level.

### Working:

It takes two inputs: the reference voltage and the feedback voltage. The feedback voltage is a scaled version of the output. The amplifier compares these two values and produces an output signal based on the difference between them. If the output voltage drops below the required level, the error amplifier increases its output to correct it. If the output voltage rises too much, it reduces the signal. This continuous adjustment helps maintain a steady output voltage under all conditions.

---

## II. Reference voltage (Vref)

### Function:

The reference voltage provides a stable and fixed value that the output voltage tries to follow.

### Working:

This voltage is designed to remain constant regardless of changes in temperature or input supply. It serves as a benchmark for the entire regulation process. The error amplifier always tries to make the feedback voltage equal to this reference value, which indirectly controls the final output voltage.

---

## III. Pass transistor

### Function:

The pass transistor controls how much current flows from the input to the output.

### Working:

It behaves like a controllable resistor. The gate of the transistor is driven by the error amplifier. When more current is needed at the output, the transistor allows more current to pass through. When less current is required, it restricts the flow. This adjustment directly controls the output voltage. The performance of this transistor also affects important parameters like dropout voltage and efficiency.

---

## IV. Compensation network (Rc and Cc)

### Function:

The compensation network ensures that the system remains stable and does not oscillate.

### Working:

Since the LDO uses a feedback loop, there is a possibility of instability if the loop is not properly controlled. The RC network introduces specific frequency characteristics that improve the phase margin. This helps the system respond smoothly to changes without causing unwanted oscillations or ringing in the output voltage.

---

## V. Feedback network (R0 and R1)

### Function:

The feedback network samples the output voltage and sends a portion of it back to the error amplifier.

### Working:

The resistors form a voltage divider. Instead of feeding the full output voltage, only a scaled-down version is sent back. This makes it easier to compare with the reference voltage. By choosing proper resistor values, the desired output voltage can be set. This network is essential for maintaining accurate regulation.

---

## VI. Output capacitor and ESR

### Function:

The output capacitor helps in smoothing the output voltage and improving stability.

### Working:

The capacitor stores energy and releases it when there is a sudden increase in load demand. This reduces voltage dips. It also filters out high-frequency noise, making the output cleaner. The ESR of the capacitor plays a helpful role by introducing a zero in the system, which improves stability and transient response.

---

## VII. Load

### Function:

The load represents the actual circuit or device powered by the LDO.

### Working:

In real applications, the load current is not constant and can change frequently. When the load increases, the output voltage tends to drop, and when the load decreases, the voltage may rise. The LDO reacts quickly to these changes by adjusting the pass transistor, ensuring that the output voltage remains stable.
