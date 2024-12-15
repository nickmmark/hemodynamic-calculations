# hemodynamic-calculations
Hemodynamic calculations are useful for quantifying the severity of cardiogenic shock and can assist in management.
This repository contains several hemodynamic calculations including Cardiac Power Output (CPO), Pulmonary Artery Pulsatility Index (PAPI).

### Cardiac power output (CPO)
Power is defined as work done per unit time. In the case of the heart, work is typically expressed as ventricular stroke work (VSW). The product of VSW and heart rate (HR) is cardiac power output (CPO).

```math
VSW = \int_{ESV}^{EDV} P_{systolic} (V)\mathrm{d}V - \int_{ESV}^{EDV} P_{diastolic} (V)\mathrm{d}V
```
```math
P_{mean arterial} = \frac{ \int_{ESV}^{EDV} P_{systolic} (V)\mathrm{d}V}{EDV - ESV}
```
```math
P_{filling pressure} = \frac{ \int_{ESV}^{EDV} P_{diastolic} (V)\mathrm{d}V}{EDV - ESV}
```

```math
stroke Volume = EDV - ESV
```

```math
VSW = (P_{mean arterial} - P_{filling pressure}) x stroke volume
```

```math
CPO = (MAP - {Filling Pressure}) x {Cardiac Output}
```

```math
CPO = \frac {(CO - RAP) x MAP}{451}
```

In situations where the RAP is relatively low, we can simplify to the standard formula:
```math
CPO = \frac {CO x MAP}{451}
```

### Pulmonary Artery Pulsatility Index (PAPI)

```math
PAPI = (PASP - PADP) / RAP
```


### References

