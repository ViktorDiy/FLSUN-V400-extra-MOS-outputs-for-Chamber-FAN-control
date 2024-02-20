# FLSUN-V400-extra-MOS-outputs-for-Chamber-FAN-control
FLSUN V400 extra MOS outputs for Chamber FAN control by MKS 3MOS module

FLSUN V400 don't has a slots for additional fans, for example for chamber exhaust fan control, but you can add 3 MOS slots by MKS 3MOS module.

MKS 3MOS module integrates 3 controllable MOS outputs. The pins and size are compatible with the stepper driver slot (E1 that empty on V400 MCU). If you want to add controllable fans or controllable LEDs (current less than 1A) to the motherboard, this module is very useful. Most motherboards with pluggable drivers are compatible, such as MKS Robin Nano series, MKS GEN_L/SGEN_L/Monster8, etc.

You can buy it for example here: https://www.aliexpress.com/item/1005003754128206.html

![image](https://github.com/ViktorDiy/FLSUN-V400-extra-MOS-outputs-for-Chamber-FAN-control/assets/147925158/5a736485-dd9e-4eb0-83b3-f774e125b7f1)
![image](https://github.com/ViktorDiy/FLSUN-V400-extra-MOS-outputs-for-Chamber-FAN-control/assets/147925158/7501e695-d46c-4413-b6e5-6d5ecfe1102e)
![image](https://github.com/ViktorDiy/FLSUN-V400-extra-MOS-outputs-for-Chamber-FAN-control/assets/147925158/82905b1c-3c0c-4bc4-92f2-a1c3ffe774dc)

MKS 3MOS scheme:
![image](https://github.com/ViktorDiy/FLSUN-V400-extra-MOS-outputs-for-Chamber-FAN-control/assets/147925158/2c46a808-5b4b-4f50-9356-8bff2c00dd59)


Driver slot should be in STEP/DIR mode (not in UART, not in SPI). You can setup it by jumpers positions on picture below.
MKS Robin NANO v2 pinout with pins that we need for this setup:
![image](https://github.com/ViktorDiy/FLSUN-V400-extra-MOS-outputs-for-Chamber-FAN-control/assets/147925158/bc5693fb-44f5-4bcb-9c13-920fd20fe80a)

![image](https://github.com/ViktorDiy/FLSUN-V400-extra-MOS-outputs-for-Chamber-FAN-control/assets/147925158/6a2a88d7-0f53-45e3-9a41-af8feda3a2cc)






So, ENABLE or EN responsible for FAN 1 control, 
    STEP for FAN 2,
    DIR for FAN 3.

Some usefull links:

https://github.com/makerbase-mks/MKS-Robin-Nano-V2.X

https://www.teamfdm.com/files/file/455-chamber-heater/

https://www.youtube.com/watch?v=81M_4skLzUM&t=367s

https://www.facebook.com/profile.php?id=100094217897627

https://youtu.be/IhrfpiFtsbw?si=Ev9Sy7TuxG35bLEd

Printer.cfg example for how to use:

[temperature_fan chamber]

pin: PA3 #STEP/DIR EN pin

max_power: 1.0

shutdown_speed: 0.0

kick_start_time: 5.0

cycle_time:0.01

off_below:0.1

sensor_type: EPCOS 100K B57560G104F

sensor_pin: PC2 #TH2 for E1 temperature sensor

min_temp: 0

max_temp: 95

target_temp: 40

control: watermark

