Big thanks to Nero for putting out this guide: https://www.youtube.com/watch?v=AtW3GqkKUz8&ab_channel=Nero3dp


Here are the steps from his video on how to connect your Raspberry Pi via Serial to your MCU. 


1. Swapping ports used by GPIO and Bluetooth:
- sudo nano /boot/config.txt
- Move the cursor to the very end and add:
- dtoverlay=pi3-miniuart-bt


2. Disabling the serial console:
- sudo nano /boot/cmdline.txt
- Look for following string (text) and delete it
- console=serial0,115200


3. Raspi-config stuff:
- sudo raspi-config
- Go to 'Interfacing Options'
- Then P6 - Serial
- Then No
- Then Yes
- Then go down to finish and reboot.


4. Rebuild your Klipper MCU firmware:
- unselecting "Use USB for communication (instead of serial). 
- Flash updated firmware to your board


5. Update your printer.cfg:
- serial: /dev/ttyAMA0
