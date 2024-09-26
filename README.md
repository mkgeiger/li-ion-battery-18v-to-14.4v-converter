# li-ion-battery-18v-to-14.4v-converter
Convert Li-ion 18V (5s) battery to Ni-Mh or Ni-Cd 14.4V for the usage in older power tools

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
