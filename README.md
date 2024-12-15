# hemodynamic-calculations
Hemodynamic calculations are useful for quantifying the severity of cardiogenic shock and can assist in management.
This repository contains several hemodynamic calculations including Cardiac Power Output (CPO), Pulmonary Artery Pulsatility Index (PAPI).

### Cardiac power output (CPO)
Power is defined as work done per unit time. In the case of the heart, work is typically expressed as ventricular stroke work (VSW).

```math
VSW = \int_{ESV}^{EDV} P_{systolic} (V)\mathrm{d}V - \int_{ESV}^{EDV} P_{diastolic} (V)\mathrm{d}V
```


```math
CPO = CO x MAP / 451
```

### Pulmonary Artery Pulsatility Index (PAPI)

```math
PAPI = (PASP - PADP) / RAP
```


### References

