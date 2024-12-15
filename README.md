# hemodynamic-calculations
Hemodynamic calculations are useful for quantifying the severity of cardiogenic shock and can assist in management.
This repository contains several hemodynamic calculations including Cardiac Power Output (CPO), Pulmonary Artery Pulsatility Index (PAPI).

## Cardiac power output (CPO)
### Derivation
Power is defined as work done per unit time. In the case of the heart, work is typically expressed as ventricular stroke work (VSW), which is the area under the pressure volume curve. The product of VSW and heart rate (HR) is cardiac power output (CPO).
![](https://github.com/nickmmark/hemodynamic-calculations/blob/main/cardiac_stroke_work_figure.png)

We can measure the volume under the curve by subtracting the diastolic integral from the systolic integral:
```math
VSW = \int_{ESV}^{EDV} P_{systolic} (V)\mathrm{d}V - \int_{ESV}^{EDV} P_{diastolic} (V)\mathrm{d}V
```
We can approximate the mean arterial pressure as follows:
```math
P_{mean arterial} = \frac{ \int_{ESV}^{EDV} P_{systolic} (V)\mathrm{d}V}{EDV - ESV}
```
```math
P_{filling pressure} = \frac{ \int_{ESV}^{EDV} P_{diastolic} (V)\mathrm{d}V}{EDV - ESV}
```

```math
stroke Volume = EDV - ESV
```
By rearranging the above equations we get:
```math
VSW = (P_{mean arterial} - P_{filling pressure}) x stroke volume
```

By multiplying by heart rate we can convert VSW to CPO:
```math
CPO = (MAP - {Filling Pressure}) x {Cardiac Output}
```

In order to make the units work (assuming CO in lpm and MAP and RAP in mmHh)
```math
CPO = \frac {(CO - RAP) x MAP}{451}
```

In situations where the RAP is relatively low, we can simplify to the standard formula:
```math
CPO = \frac {CO x MAP}{451}
```

### Significance


### Calculator


## Pulmonary Artery Pulsatility Index (PAPI)
### Derivation
```math
PAPI = (PASP - PADP) / RAP
```

### Signficance


### Calculator


### References

