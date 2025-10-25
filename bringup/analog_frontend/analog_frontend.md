# Test-setup
The test-setup we use in order to select which of the 2 methods of isolation we'd rather select:

- RJ45 with blocking capacitors
- RJ45 with isolation

requires
## Signal generation
A way to apply signals to the RJ45
- So some kind of signal generator capable of generating signals with
- An amplitude of 1.65 V
- Low-impedance (capable of delivering a few mA)
- High-frequency (up to 5 MHz)
- Preferably generating 2 differential signals
- Not too expensive

Something like:
- https://www.otronic.nl/en/ad9850-dds-signal-generator-module.html


## Analog Measurement
A way to measure
- Signals between 100 kHz and 35 MHz (should be doable with oscilloscope)
- Could be done with a VNA
	- The freuency range of the LiteVNA64 is between 50 kHz and 6.3 GHz
Probes are installed along the traces leading to the ADC, so
- A U.FL. to coax (fitting for a VNA)
	- NanoVna
- A U.FL. to BNC connector, to fit into an oscilloscope

However the main issue here is the differential nature of the signal, requiring special measuring equipment

## ADC digital measurement
Since the FPGA-BGA package shorted, we need to either 
- solder to the ADC feet
- Connect small clips to the ADC feet

Issues here
- fast rise/fall times will lead to oscillations.
	- Can be solved for the ADC data out
	- Probably less easy to solve for the data-in.

# Improvements for version 2
## Differential signals
At an ADC input, high frequency signals should ALWAYS be single ended.
- It makes it easier to measure
- It makes it easier to transport (single coax, single shield)

