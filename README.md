# Caravel Analog User

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) [![CI](https://github.com/efabless/caravel_user_project_analog/actions/workflows/user_project_ci.yml/badge.svg)](https://github.com/efabless/caravel_user_project_analog/actions/workflows/user_project_ci.yml) [![Caravan Build](https://github.com/efabless/caravel_user_project_analog/actions/workflows/caravan_build.yml/badge.svg)](https://github.com/efabless/caravel_user_project_analog/actions/workflows/caravan_build.yml)

---

| :exclamation: Important Note            |
|-----------------------------------------|

## Please fill in your project documentation in this README.md file 

Description of the Design Idea:*
According to the World Health Organization's Cancer Tomorrow report [1] based on 2022 data, skin cancer is among the most common cancers in the world. The report also projects a 94.9% increase in the incidence of non-melanoma skin cancers by 2045, representing the largest increase worldwide among all types of cancer. Early detection is critical for effective treatment, but accurately diagnosing skin lesions remains a challenging task due to its various sub-types. Healthcare professionals often resort to unnecessary, costly, and invasive procedures such as biopsies due to insufficient information available during visual examinations to conclusively classify skin lesions as either benign or malignant.
Electrical impedance spectroscopy (EIS) is a promising technique to distinguish between benign and malignant skin lesions, as demonstrated in clinical studies using commercial devices like Nevisense [2], [3]. Nonetheless, their cost and demand for specialized training limits the widespread adoption by healthcare professionals. Silicon miniaturization can be used to democratize the use of EIS in skin cancer detection by lowering manufacturing costs in the design of a bioimpedance analog front-end (AFE).
The proposed bioimpedance AFE employs a 4-electrode configuration for bioimpedance measurement, in which a current generator circuit generates differential sine currents that are injected into the body through two electrodes. The other two electrodes measure the resulting voltage. A read-out circuit then calculates the magnitude and phase of the bioimpedance transfer function based on the measured voltage.
The current generator uses Direct Digital Synthesis (DDS) to generate the source and sink currents. The approach in this research employs digital circuits for the phase accumulator, LUT and control, along with analog circuits for a 6-bit current-steering DAC and an output differential switch. The current generator has already been developed in other CMOS processes. The VHDL files for the digital part are already available, the analog the current-steering DAC and differential switch must be resized to sky 130nm.
The readout circuit uses differential signals throughout the processing stages. It employs two instrumentation amplifiers (INAs): one captures the voltage between pick-up electrodes, while the other measures the voltage across a known current-sense resistor (RI-SENSE), as shown in the block diagram.
The phase detector converts the voltages into square waves using clockless comparators. An XOR gate then produces a pulse signal, where the pulse width represents the phase introduced by the unknown impedance at the test frequency. The peak detector provides the magnitude measurement using a full-wave rectifier circuit followed by a low-pass filter.
Currently, the design of the peak and phase detectors is still in progress. The circuit that has been completed is the instrumentation amplifier, which is the first stage of the readout system. The proposed INA incorporates a fully differential difference amplifier already implemented in sky 130nm process, in the first edition of UNIC-CASS. Voltage and current reference circuits will also be included to ensure correct operation and stability of the systems under varying conditions.

[1] World Health Organization, “Cancer Tomorrow,” 2022. Accessed: Jun. 08, 2024. [Online]. Available: https://gco.iarc.fr/tomorrow/en/dataviz/bars
[2] J. Malvehy et al., “Clinical performance of the Nevisense system in cutaneous melanoma detection: An international, multicentre, prospective and blinded clinical trial on efficacy and safety,” British Journal of Dermatology, vol. 171, no. 5, pp. 1099–1107, Nov. 2014, doi: 10.1111/bjd.13121.
[3] “Nevisense Clinical Reference Guide The EIS Method and How to Interpret the Nevisense Result ii Nevisense Clinical Reference Guide Nevisense Clinical Reference Guide iii.”

:warning: | Use this sample project for analog user projects. 
:---: | :---

---

Refer to [README](docs/source/index.rst) for this sample project documentation. 
