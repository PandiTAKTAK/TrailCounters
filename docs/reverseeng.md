# Reverse Engineering

There's not a huge amount of available data for the trail counter construction.

## Data Cube

The data cubes are the elements used to capture trail count. These are periodically recovered and the data is dumped off them.

They're a resin potted unit making them inconvenient to directly inspect.

### Initial Info

- 8 pins on 2.54 pitch headers.
- 2 rows, pin 7 blanked.

### Investigation

X-Ray shows data cube is a 8-pin DIP with the 2x4p headers soldered directly to the pins.

*Likely* to be SPI flash.

![Data cube](_media\datacube.png)

#### Actions

None -> The reader will provide the interfacing data in the first instance 

## Serial Link

UART to USB

### Initial Info

### Investigation

![Maxim part](_media\max3222cpn.png)

- Houses Maxim [MAX3222CPN](https://pdfserv.maximintegrated.com/en/ds/MAX3222-MAX3241.pdf)
  - Level translator 3v0 to 5v5
- P14 & 15 shorted - Likely being used as an ident

![Pinout](_media\serialpinout.png)

#### Actions

TBD -> Sniff UART comms between PC and Reader

## Reader

Used to extract data from the data cubes.

### Initial Info

- Based on PIC16F84.
- Comms is via UART.

### Investigation

#### Actions

TBD -> Probe pins for VCC and 0V
TBD -> Identify clock and data lines
TBD -> 
TBD -> Sniff UART comms between PC and Reader

## Date Setter

Used for setting epoch on the data cubes at installation time.

### Initial Info

TBD

### Investigation

#### Actions

TBD -> Investigate

## Base Station

The base station is buried near the trail in order to conceal the equipment.

### Investigation

#### Actions

TBD -> Probe pins

## Pressure Pad

The pressure pad is buried underneath the trail surface. Likely a piezo-electric trigger into the base-station.

### Investigation

#### Actions

TBD -> Probe pins