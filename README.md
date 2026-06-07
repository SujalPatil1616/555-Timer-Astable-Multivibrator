# 555 Timer Astable Multivibrator using LTspice

## Overview

This project demonstrates the design and simulation of a 555 Timer IC configured in Astable Mode using LTspice. In this configuration, the 555 timer operates as a free-running oscillator and continuously generates a square-wave output without requiring any external trigger signal. The output frequency is determined by two resistors and a timing capacitor connected to the timer circuit.

The simulation analyzes both the output waveform and the charging/discharging behavior of the timing capacitor.

---

## Components Used

- NE555 Timer IC
- DC Supply Voltage: 5 V
- Resistor R1: 1 kΩ
- Resistor R2: 10 kΩ
- Timing Capacitor C3: 50 nF
- Control Voltage Capacitor C2: 50 nF
- Supply Bypass Capacitor C1: 10 nF

Simulation Command:

```text
.tran 5m
```

---

## Circuit Diagram

<img src="circuit_diagram.png" width="700">

---

## Working Principle

The 555 timer contains internal comparators that monitor the voltage across the timing capacitor. During operation, the capacitor repeatedly charges through resistors R1 and R2 and discharges through resistor R2 via the internal discharge transistor connected to Pin 7.

For a 5 V supply:

- Lower Threshold = 1/3 VCC ≈ 1.67 V
- Upper Threshold = 2/3 VCC ≈ 3.33 V

When the capacitor voltage reaches approximately 3.33 V, the timer output switches LOW and the discharge transistor turns ON. The capacitor then discharges until its voltage falls to approximately 1.67 V. At this point, the timer output switches HIGH and the capacitor begins charging again.

This charging and discharging cycle repeats continuously, producing a square-wave output.

---

## Frequency Calculation

### Time High

TH = 0.693 × (R1 + R2) × C

TH = 0.693 × (1k + 10k) × 50nF

TH ≈ 0.381 ms

### Time Low

TL = 0.693 × R2 × C

TL = 0.693 × 10k × 50nF

TL ≈ 0.347 ms

### Total Period

T = TH + TL

T ≈ 0.728 ms

### Output Frequency

f = 1 / T

f ≈ 1.37 kHz

---

## Output Waveform

<img src="output_waveform.png" width="700">

## Observation

The output voltage alternates between 0 V and 5 V, producing a continuous square-wave signal. The waveform remains stable throughout the simulation and demonstrates the oscillator behavior of the 555 timer. The measured frequency is approximately 1.36 kHz, which closely matches the theoretical value.

---

## Capacitor Voltage Waveform

<img src="https://github.com/SujalPatil1616/555-Timer-Astable-Multivibrator/blob/main/Capacitor_Waveform.png" width="700">

## Observation

The timing capacitor repeatedly charges and discharges between approximately 1.67 V and 3.33 V. When the capacitor voltage reaches 2/3 VCC, the discharge transistor turns ON and the capacitor begins discharging. When the voltage falls to 1/3 VCC, the capacitor starts charging again. This repeating cycle determines the output frequency of the oscillator.

---

## Results Comparison

| Parameter | Output Waveform | Capacitor Waveform |
|------------|----------------|-------------------|
| Voltage Range | 0 V to 5 V | 1.67 V to 3.33 V |
| Waveform Type | Square Wave | Charge/Discharge Curve |
| Function | Signal Generation | Frequency Control |
| Frequency | ≈ 1.36 kHz | = 1.36 KHz |

---

## Applications

- Clock Pulse Generation
- LED Flashers
- PWM Circuits
- Tone Generators
- Delay Circuits
- Oscillator Circuits
- Embedded System Timing Applications
- Signal Generation Circuits

---

## Conclusion

The LTspice simulation successfully demonstrates the operation of a 555 Timer IC in Astable Mode. The timing capacitor continuously charges and discharges between 1/3 VCC and 2/3 VCC, causing the output to switch between HIGH and LOW states. The circuit generates a stable square-wave signal with a frequency of approximately 1.36 kHz. This project provides a practical understanding of timer-based oscillators and waveform generation circuits commonly used in embedded systems and electronics applications.

---

## Software Used

- LTspice XVII / LTspice 26
