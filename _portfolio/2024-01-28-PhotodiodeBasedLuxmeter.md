---
title: "Photodiode-Based Luxmeter with Arduino and AVR Assembly"
excerpt: "Design and firmware implementation of a complete luxmeter — from analog signal conditioning to AVR Assembly embedded code — measuring light intensity in klux with battery monitoring."
collection: portfolio
---

## Overview
Developed for the *Progettazione di Dispositivi Biomedici Programmabili (PDBP)* lab course at Politecnico di Torino, this project consisted of designing and building a complete luxmeter system, spanning analog signal conditioning to embedded firmware. The system measures light intensity in klux, displays the reading on three 7-segment digits, and monitors battery voltage.

## System Specifications
- **Measurement range**: 0–6.55 klux (design target of 9.99 klux, ultimately limited by op-amp offset)
- **Sampling period**: ~1000 ms for both light intensity and battery voltage
- **Display**: 3-digit 7-segment display (hundreds, tens, units in klux)
- **Battery alert**: LED indicator triggered when voltage drops below a 4.2 V threshold

## Hardware Design
- **Light sensor**: SFH203 photodiode in a transresistance (I–V converter) configuration
- **Amplifier**: TL081 op-amp, selected for availability; its relatively high offset (~1.52 V) was compensated in software via a look-up table
- **Feedback resistor**: 4084 Ω (3820 Ω + 264 Ω in series, measured)
- **ADC reference**: external 3.3 V (Vref) from a stabilised power supply
- **Microcontroller**: Arduino UNO (ATmega328P), powered at 7 V via Vin
- **Clock**: internal 16 MHz, divided by 16 to a 1 MHz operating frequency

## Firmware (AVR Assembly)
- **Timer Counter 0**: interrupt-driven timing, overflowing approximately every 20 ms (prescaler 1024)
- **ADC**: 8-bit conversions with left-justified result, read on two channels (battery on ADC0, photodiode on ADC1)
- **Look-up table**: 256-entry flash table mapping ADC values to klux digits (hundreds, tens, units); the first 116 entries are zeroed to compensate for the op-amp offset
- **Display driver**: multiplexed 7-segment control through a BCD decoder (PD0–PD6), with latch-enable (LE) strobing
- **Battery subroutine**: threshold comparison on the ADC reading (TSH_BAT = 217, corresponding to 4.2 V), with flag-based LED control

## Calibration
End-point calibration was carried out against a portable reference luxmeter:

- **Full-scale condition**: ~9.8–9.99 klux (torch illumination)
- **Measured output voltage**: 2.80 V
- **Measured sensitivity**: S = 68 μA/klux
- **Maximum achievable range**: 6.55 klux, constrained by the TL081 offset consuming part of the available dynamic range

## Tools & Technologies
AVR Assembly · Arduino UNO (ATmega328P) · Analog circuit design · EasyEDA (schematic) · Breadboard prototyping · Multimeter calibration

## Team
S. Maffei, V. Tarditi, Matteo Giovanni Traverso

## Download
📄 [Download full report](/files/Luxmetro con fotodiodo per luce continua.pdf)