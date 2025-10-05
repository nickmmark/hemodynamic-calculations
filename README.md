# hemodynamic-calculations
Hemodynamic calculations are useful for quantifying the severity of cardiogenic shock and can assist in management.
This repository contains several hemodynamic calculations including Cardiac Power Output (CPO), Pulmonary Artery Pulsatility Index (PAPI).

## Cardiac power output (CPO)
Cardiac power output (CPO) is a holistic measure of the heart's pumping ability, calculated by multiplying cardiac output (blood flow) by mean arterial pressure (blood pressure), essentially representing the rate of energy produced by the heart as it pumps blood throughout the body. This is analogous to the basic hydraulic flow formula `power` = `pressure` x `flow` CPO is considered a more comprehensive indicator of cardiac function compared to cardiac output alone, as it considers both pressure and flow.

### Derivation
`Power` is defined as `work` done per unit time. In the case of the heart, `work` is typically expressed as `ventricular stroke work` (VSW), which is the area under the pressure volume curve. The product of VSW and heart rate (HR) is `cardiac power output` (CPO).
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

By multiplying by heart rate (HR) we can convert `VSW` to `CPO`:
```math
CPO = (MAP - {Filling Pressure}) x {Cardiac Output}
```

In order to make the units work (assuming `CO` in lpm and `MAP` and `RAP` in mmHg) we need to divide by 451:
```math
CPO = \frac {(CO - RAP) x MAP}{451}
```

In situations where the `RAP` is relatively low (e.g. <10), we can simplify to the standard formula:
```math
CPO = \frac {CO x MAP}{451}
```

### Significance
A normal cardiac power output (CPO) is between 0.8 and 1.1 watts.
A CPO of less than 0.6 watts is a sign of hemodynamic compromise and is associated with a higher risk of mortality.

### Calculator
There are two versions of the calculator app - one that includes RAP and another that does not. For most situations where RAP is <10 we can ignore it and use the simpler calculator.


![](https://github.com/nickmmark/hemodynamic-calculations/blob/main/CPO_calculator_demo.gif)

Demonstration of the web-based calculator



## Pulmonary Artery Pulsatility Index (PAPI)
The Pulmonary Artery Pulsatility Index (PAPI) is related to - but is not a direct measure of - right ventricular function. Several factors influence PAPI including `RV stroke volume`, `Pulmonary artery compliance`, `Right Atrial Pressure`, and `Pulmonary Artery Wedge Pressure`.

### Derivation
The Pulmonary Artery Pulse Pressure (PAPP) is defined as the difference of systolic and diastolic PA pressures:
```math
PAPP = PASP - PADP
```

Compliance is:
```math
Compliance = \frac{\Delta Volume}{\Delta Pressure}
```

And pulmonary artery compliance is:
```math
Compliance_{PA} = \frac{RV Stroke Volume}{PAPP}
```

Thus either ***increasing*** `RV stroke volume` or ***decreasing*** `pulmonary artery capacitance` (PAC) will ***increase*** `PAPP`.
Pulmonary arterial capacitance (PAC) has a hyperbolic relationship with pulmonary vascular resistance (PVR). The product of PAC and PVR is the pulmonary arterial time constant (RC time), defined as the time it takes for the pulmonary artery pressure to drop by 63%.

```math
PAPI = \frac{(PASP - PADP)}{RAP}
```

### Signficance
A PAPI < 0.9 is suggestive of Right Ventricular Failure. A PAPI < 0.9 is associated with an increased risk mortality or requiring RV mechanical circulatory support.

### Calculator
A simple HTML based calculator that can be embedded in a website.

### Disclaimer
This code is provided "as is", without warranty of any kind. Double check any calculations. See the attached license for more information about the MIT License.

### References
- Lim HS. ***[Cardiac Power Output Revisited](https://doi.org/10.1161/CIRCHEARTFAILURE.120.007393)*** _Circ Heart Fail._ 2020
- Lim HS, Gustafsson F. ***[Pulmonary artery pulsatility index: physiological basis and clinical application.](https://onlinelibrary.wiley.com/doi/full/10.1002/ejhf.1679)*** _Eur J Heart Fail._ 2020
- Korabathina R _et al_, ***[The pulmonary artery pulsatility index identifies severe right ventricular dysfunction in acute inferior myocardial infarction](https://pubmed.ncbi.nlm.nih.gov/21954053/)***. _Catheter Cardiovasc Interv._ 2012
- Fincke _et al_, ***[Cardiac power is the strongest hemodynamic correlate of mortality in cardiogenic shock: a report from the SHOCK trial registry](https://pubmed.ncbi.nlm.nih.gov/15261929/). _J Am Coll Cardiol._ 2004
- Mendoza DD, Cooper HA, Panza JA. ***[Cardiac power output predicts mortality across a broad spectrum of patients with acute cardiac disease](https://pubmed.ncbi.nlm.nih.gov/17307413/).*** Am Heart J. 2007
