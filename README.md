# Universal Timing Check Board (UTCB)
###### This repo acts as the digital storage of all associated developments (e.g. firmware, pcb development, CAD) and related documentation (e.g. schematic captures, pictures, testing data) to the "Universal Timing Check Board". This device acts as a sister companion to circuit testing for analog voltage checks and timing. Inspiration for board function and design is from previous revisions of an analog based brake system plausiblity device, however, this device is more general purpose and for my personal use. 

Current Layout: 
![image](https://user-images.githubusercontent.com/126422709/229501473-1ab97b0f-fc82-4e52-a410-ef2fe6fd8bfa.png)
![image](https://user-images.githubusercontent.com/126422709/229501510-a540bbb2-5520-4147-bdef-20f445f4ef17.png)

## Board Functionality
- Check if an upper threshold is met. (0v to 12v)
    - Multichannel Comparator check
- Check if a lower threshold is met.
    - Multichannel Comparator check (0v to 12v)
- Check if mid threshold comparison between 6 signals is met. 
    - Mid-threshold voltage set via 6 potentiometers (0v to 12v)
- Drive a failure mode signal out from either signals (Within the range of 3.3-12v)
- Give Flashing Red Light when output failure is detected. Otherwise Solid Red.
- Optional: Has breakout OLED slot for visualizing data in real time with bluetooth connected transmitter. Most likely will use STM32 for MCU. 
    
## Board Connection Points

Main PWR: 
- 12V Power In Connector (Gets reduced to 3.3v via regulator for central comparator logic)
- Final PWR voltage needs to be regulated (Using off the shelf dc/dc converters with built-in regulation)

Signal Connections (For reading)
- Terminal block connection points (6P header) for direct wire feeds. 
- OptionaL: For signal voltage reading: Has ribbon cable attachment to breadboard for data collection (but no direct programmable element on-board). 
- For board debugging: Set test points to grip onto for PWR points, Comparator Outputs, and final failure outputs. 
- Indivdual signals, logic set positions, threshold voltages are passed through to the data collection slot for telemetry. 

## Purpose

- Allows me to isolate analog logic voltages on an offboard device or PCB. 
- Allows me to clearly indicate where faulty logic is based on physical tuning via potentiometers. 
- Gives me an automated way of doing logic checks over set number of iterations on the device under test. 

## What to do next
- Add visual LED indicator for each comparator logic output
- Add optional telemetric side port
- Need to reposition test points so as to not accidently short to pot pins.

