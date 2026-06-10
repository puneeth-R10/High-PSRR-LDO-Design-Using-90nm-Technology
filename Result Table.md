# Result Table
---


<div align="center">

<table>
<tr>
<th>Parameter</th>
<th>Proposed Work</th>
</tr>

<tr>
<td align="center">Year</td>
<td align="center">2026</td>
</tr>

<tr>
<td align="center">Technology (nm)</td>
<td align="center">90</td>
</tr>

<tr>
<td align="center">Pass Transistor</td>
<td align="center">PMOS</td>
</tr>

<tr>
<td align="center">Input Voltage (V)</td>
<td align="center">1.8</td>
</tr>

<tr>
<td align="center">Output Voltage (V)</td>
<td align="center">1.704</td>
</tr>

<tr>
<td align="center">Dropout Voltage (mV)</td>
<td align="center">96</td>
</tr>

<tr>
<td align="center">Maximum Load Current</td>
<td align="center">100 µA</td>
</tr>

<tr>
<td align="center">Quiescent Current (µA)</td>
<td align="center">297.7</td>
</tr>

<tr>
<td align="center">Power Consumption (µW)</td>
<td align="center">986</td>
</tr>

<tr>
<td align="center">Line Regulation (mV/V)</td>
<td align="center">0.146</td>
</tr>

<tr>
<td align="center">Load Regulation (mV/mA)</td>
<td align="center">1.26</td>
</tr>

<tr>
<td align="center">PSRR @ 10 kHz</td>
<td align="center">-80.76 dB</td>
</tr>

<tr>
<td align="center">PSRR @ 100 kHz</td>
<td align="center">-80.29 dB</td>
</tr>

<tr>
<td align="center">PSRR @ 1 MHz</td>
<td align="center">-78.39 dB</td>
</tr>

<tr>
<td align="center">Gain (dB)</td>
<td align="center">79.02</td>
</tr>

<tr>
<td align="center">Phase Margin</td>
<td align="center">68.65°</td>
</tr>

<tr>
<td align="center">Settling Time</td>
<td align="center">5 µs</td>
</tr>

<tr>
<td align="center">Overshoot</td>
<td align="center">0.5 mV</td>
</tr>

<tr>
<td align="center">Undershoot</td>
<td align="center">0.5 mV</td>
</tr>

<tr>
<td align="center">Temperature Range</td>
<td align="center">40°C to 125°C</td>
</tr>

<tr>
<td align="center">Process Corners Verified</td>
<td align="center">FF, FS, SF, SS, TT</td>
</tr>

</table>

</div>

---

The performance comparison presented in the table demonstrates that the proposed CMOS LDO regulator achieves competitive performance when compared with recently reported LDO designs. Implemented using 90 nm CMOS technology with a PMOS pass transistor, the proposed regulator operates from a 1.8 V supply and provides a regulated output voltage of 1.704 V while maintaining a low dropout voltage of 96 mV.

The regulator exhibits excellent regulation characteristics, achieving a line regulation of 0.146 mV/V and a load regulation of 1.26 mV/mA, indicating strong immunity to supply and load variations. Furthermore, the design provides high power-supply noise rejection with PSRR values of −80.76 dB at 10 kHz, −80.29 dB at 100 kHz, and −78.39 dB at 1 MHz, making it suitable for noise-sensitive analog and mixed-signal applications.

The proposed LDO achieves a high loop gain of 79.02 dB and a phase margin of 68.65°, ensuring robust closed-loop stability and reliable operation. The transient performance is also satisfactory, with a settling time of 5 µs and extremely low overshoot and undershoot values of 0.5 mV, demonstrating excellent dynamic response.

In addition, the regulator has been verified across multiple process corners including FF, FS, SF, SS, and TT, as well as supply voltage and temperature variations, confirming the robustness of the design against process, voltage, and temperature (PVT) fluctuations. The gain across all corners remains within 60.26 dB to 77.67 dB, ensuring stable operation under worst-case conditions.

The quiescent current of 297.7 µA and total power consumption of 986 µW indicate that the regulator is capable of delivering reliable performance while maintaining reasonable power efficiency. The design also supports load currents up to 100 µA, making it suitable for low-power integrated systems and sensor-based applications.

Overall, the proposed CMOS LDO regulator offers a balanced combination of low dropout voltage, high loop gain, good stability margins, excellent regulation performance, strong PSRR, and reliable operation across all process corners, making it a suitable candidate for low-power integrated power management applications.
