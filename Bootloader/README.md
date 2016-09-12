# GyroPalm Bootloader
These are the standard procedures to burn the bootloader for a GyroPalm board.
You will strictly need Arduino v1.0.5 IDE to perform these procedures.

1. Copy the *mighty-1284p* folder to *Arduino/hardware*
2. Copy the folders inside *mighty-1284p\patched-libs\official* to the Arduino libraries.
3. Plug in a regular Arduino board (with ISP headers attached) to be used as ISP Programmer via USB.
4. Do not connect the GyroPalm PCB yet. Open the Arduino IDE.
4. In the program, click *File > Examples > ArduinoISP*
5. Choose the Arduino COM port in *Tools > Serial Port*
6. Upload the sketch to the board, and disconnect the USB cable.
7. Wire the Arduino ISP headers to the GyroPalm board as shown:
```
GyroPalm without  |  Arduino as ISP
   bootloader     |   programmer
__________________|________________
ICSP pin#1 (MISO) |      D12
ICSP pin#2 (+5V)  |      5V
ICSP pin#3 (SCK)  |      D13
ICSP pin#4 (MOSI) |      D11
ICSP pin#5 (RST)  |      D10
ICSP pin#6 (GND)  |      GND
__________________|________________
```
8. Plug in the Arduino ISP programmer into the PC again.
9. In the Arduino program, click *Tools > Boards > MightyMini 1284p @ 8MHz*
10. In the Arduino program, click *Tools > Programmer > Arduino as ISP*
11. Now, you can burn the bootloader by clicking *Tools > Burn Bootloader*
	If you get an error, try this step again until you see frequent blinking LEDs.
12. Once the bootloader is burned, disconnect ISP headers from both boards.
13. Plug in the GyroPalm board via USB, check for the Serial Port.
14. If a new COM port shows up, you may now upload to the GyroPalm board with GyroPalm IDE.
