# Universal Timing Check Board (UTCB)
###### This repo acts as the digital storage of all associated developments (e.g. firmware, pcb development, CAD) and related documentation (e.g. schematic captures, pictures, testing data) to the "Universal Timing Check Board". This device acts as a sister companion to circuit testing for analog voltage checks and timing. Inspiration for board function and design is from previous revisions of an analog based brake system plausiblity device, however, this device is more general purpose and for my personal use. 


Image below shows a general esimate of how I intended the board to look like and inspired by (although to be at a much much smaller dimensional board footprint)

![image](https://user-images.githubusercontent.com/126422709/221457139-57d0c613-f147-428f-b165-ee71c0b4f5a0.png)

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
- Finish PCB traces (only 40% done)

Current Layout: 
![image](https://user-images.githubusercontent.com/126422709/227051652-c50f58ab-9e79-4286-8eaf-12260f3d0122.png)

Example Comparator Logic Stage
<img width="878" alt="image" src="https://user-images.githubusercontent.com/126422709/227051745-60926260-d7ca-4f40-9d2b-4918875d336f.png">



