As shown in Figure 2, analog LDOs basically consist of a P-type pass transistor ($M_{\text{P}}$), an error amplifier (EA), and a load capacitor ($C_{\text{L}}$). If $I_{\text{L}}$ or $V_{\text{IN}}$ changes, $C_{\text{L}}$ initially compensates for the variation to mitigate immediate fluctuations in $V_{\text{OUT}}$. In the second step, the feedback loop operates to regulate the $M_{\text{P}}$ current ($I_{\text{OUT}}$) to match the new value of $I_{\text{L}}$, thereby restoring $V_{\text{OUT}}$ to the same value as the reference voltage ($V_{\text{REF}}$).

<p align="center">
  <img src="https://github.com/user-attachments/assets/2aa7077e-e05d-4812-8885-4ce01e7489a0" alt="Basic structure of an LDO" width="540" />
  <br>
  <em>[Figure 2: Basic structure of an LDO]</em>
</p>

For example, as shown in the top of Figure 3, when $I_{\text{L}}$ changes from minimum $I_{\text{L}}$ ($I_{\text{Lmin}}$) to maximum $I_{\text{L}}$ ($I_{\text{Lmax}}$), the current from $C_{\text{L}}$ ($I_{C_{\text{L}}}$) initially compensates for $I_{\text{L}}$, which causes a temporary decrease in $V_{\text{OUT}}$. Following this, the negative feedback loop responds: the input difference of the EA decreases due to the drop in $V_{\text{OUT}}$, and this reduction is amplified by the EA gain ($A_{\text{EA}}$), driving a sharp decrease in the gate node voltage ($V_{\text{G}}$) of $M_{\text{P}}$. This increase in $|V_{\text{GS}}|$ of $M_{\text{P}}$ results in a significant increase in $I_{\text{OUT}}$, allowing $M_{\text{P}}$ to supply a current equal in quantity to $I_{\text{L}}$, and thus returning $V_{\text{OUT}}$ to nearly the same value as $V_{\text{REF}}$. As shown in the bottom of Figure 2, when $I_{C_{\text{L}}}$ compensates for $I_{\text{L}}$ initially, $V_{\text{OUT}}$ decreases, but as the portion of $I_{\text{OUT}}$ compensation increases, $V_{\text{OUT}}$ recovers back to the targeted value of $V_{\text{REF}}$.

<p align="center">
<img width="525" height="431" alt="Image" src="https://github.com/user-attachments/assets/1df0642e-3532-4821-b842-1e6a89428e39" />
<p align="center">
<img width="535" height="442" alt="Image" src="https://github.com/user-attachments/assets/cbe1162c-c7a8-4491-906a-2d00ab2bbc63" />
<br>
  <em>[Figure 3: LDO operation when IL changes from ILmin to ILmax.]</em>
</p>
