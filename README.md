# Li-ion 18V to 14.4V battery converter
When you still have some older power tools lying around, which have defective NiMH- or NiCd-batteries and you want to reactivate them with newer Li-ion batteries, you are here on the right project page.
Those old power tools were often powered with 14.4V (12 cells @ 1.2V), whereas nowadays the power tools are powered with 18V (5 Li-ion cells @ 3.6V).
The circuit below is a converter from 18V to 14.4V. It implements also a deep discharge protection for the Li-ion battery. In order to not cause a permanent damage to the 18V Li-ion battery, it should not be discharged below ~16V (3.2V per cell).
For sure this simple circuit does not supervise the voltage of each single cell because a power tools' Li-ion battery typically does not offer this feature. 
The voltage thresholds for powering on and off can be calculated with the formulas in chapter `Simulation`. The circuit provides the potentiometer R1 to exactly trim these voltage thresholds.
Also I recommend a heatsink for the mosfet and the diodes to not overheat those parts (depending on the used power tool several amps can flow).

### Schematic

![Schematic](/Schematic/Schematic.png)

### Simulation

The circuit has been simulated with the freeware LTspice. Because some part models were missing in the provided standard library I added those models in folder ![LTspice](/LTspice/).

The switching-on threshold voltage can be calculated with:
`U_on = 2.5V * (R2 + (R1||R4)) / (R1||R4)`

![SwitchOnThreshold](/LTspice/SwitchOnThreshold.png)

The switching-off threshold voltage can be calculated with:
`U_off = 2.5V * (R1 + (R2||R4)) / R1`

![SwitchOffThreshold](/LTspice/SwitchOffThreshold.png)
