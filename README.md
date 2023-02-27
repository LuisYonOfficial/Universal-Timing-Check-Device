# UTCB
This repo acts as the digital storage of all associated developments (e.g. Circuit Design, Pictures, CAD) and related documentation to the "Universal Timing Check Board". This device acts as a sister companion to circuit testing for analog voltage checks and timing. 

** Board Functionality ** 

- Check if an upper threshold is met. (0v to 12v)
    - Comparator check
- Check if a lower threshold is met.
    - Comparator check (0v to 12v)
- Check if mid threshold comparison between 2-4 signals is met. 
    - Mid-threshold voltage set via 2- 4 potentiometers (0v to 12v)
- Drive a failure mode signal out from either signals (12v, 7.5v, 3.3v, 0v)
- Have RGB LEDs that glow based on what failure condition per signal is failed or if there’s a net pass. These are tied to comparators? Might be tricky. 
    - Red: Threshold failure
    - Orange: Timing Failure
    - Green: No Failure
    
    ![image](https://user-images.githubusercontent.com/126422709/221456646-b8c6f140-ab58-4f6d-94e5-a3945f314592.png)

** Board Connection Points ** 

Main PWR: 
- PWR through wall outlet (Expands to 12v and 7.5v option for logic) 
    - Needs AC to DC conversion with voltage step down.  
- Final PWR voltage needs to be regulated (Off the shelf chip) 

Signal Connections (For reading)
- Terminal block connection points (4P header) for direct wire feeds. 
- For signal voltage reading: Has ribbon cable attachment to breadboard for data collection (but no direct programmable element on-board). 
- For board debugging: Set test points to grip onto for PWR points, Comparator Outputs, and final failure outputs. 

** Purpose ** 

- Allows me to isolate analog logic voltages on an offboard device or PCB. 
- Allows me to clearly indicate where faulty logic is based on physical tuning via potentiometers. 

---> What to do next <---
Finish basic logic check circuitry for 5 signals. Need to find a comparator chipset rated for 12v and higher. 
Develop basic logic switch circuitry for determining if 3.3v, 5v, 7.5v, or 12v is being utilized for logic. 

