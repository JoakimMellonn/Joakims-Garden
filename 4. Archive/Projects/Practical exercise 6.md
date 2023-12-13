
1. Voltage stepping
	1. 45V or 40V maximum voltage (40V according to front page, 45V according to specs)
	2. Efficiency when stepping down from 9V to 3.3V is about 73/74%
	3. ACT4523 https://www.mouser.com/datasheet/2/631/ACT4523_Datasheet-345999.pdf
2. RFID reading range
	1. https://www.adiglobal.dk/Product/N54504-Z106-A100?setcontextlanguagecode=da-DK
		1. Datasheet on page
3. Transistor base current
	1. Base current 120 mAdc
	2. Max current draw from GPIO is 40mA https://electronics.stackexchange.com/questions/494141/voltage-from-io-pin-at-max-current
	3. Step up current?????????
4. Motor specs and dimensions
	1. https://www.digikey.dk/da/products/detail/johnson-motor/NF123G-302/12723724
		1. 9V DC Motor (20,32 mm diameter)
5. Actuation possibilities
	1. I would use this two stepper motor controller on one board: https://arduinotech.dk/shop/l9110s-h-bridge-dual-dc-stepper-motor-driver-controller/
	2. I would also use a power supply, to make sure the motors get enough power: http://www.handsontec.com/dataspecs/mb102-ps.pdf
6. ESP Lookup
	1. Yes the ESP32 support I2C communication
	2. Yes it has 34 programmable GPIOs, many of them are accessible as pins
	3. The V3 ESP32 does not support 5ghz WiFi
	4. Yes it has 5 power modes, one of them Deep-Sleep
7. Sensing force
	1. I would use this which supports up to 100N of force: https://www.digikey.dk/htmldatasheets/production/2381828/0/0/1/force-sensitive-resistor-fsr-.html
8. Raspberry Pi lookup
	1. Yes the Raspberry Pi has plenty of GPIO pins
	2. No the Raspberry Pi doesn't have ADC functionality
	3. I would follow this guide using the MCP3008 chip: https://learn.adafruit.com/raspberry-pi-analog-to-digital-converters/mcp3008
9. Microcontrollers for Mangfoldighed
	1. First important difference is the non-volatile memory size, the ATtiny85 has 8KB while the ATMega328 has 32KB
		1. More storage for bigger programs
	2. 2 vs 6 PWM channels
	3. 6 GPIO pins vs 23 GPIO pins
	4. The ATtiny85 has lower power consumption, Active mode min consumption: 0,00054W vs 0,0045W
	5. ATMega328 has ADC pins, they good
10. Lights, Datasheet, Action!
	1. According to this random page it seems to be 60mA per LED, so it would be 480mA for eight LEDs: https://www.eevblog.com/forum/projects/ws2812b-leds-power-consumption/
	2. According to the datasheet it takes in 5V, so you should step down the voltage from 9V to 5V
	3. FastLED is a widely used library for many LED strips: https://fastled.io/
11. Bass Blastin'
	1. I found this surface transducer, which works in the frequency range 10-80hz: https://www.daytonaudio.com/product/1245/bst-1-high-power-pro-tactile-bass-shaker-50-watts
12. Helping your future selves
	1. That sounds like a future me problem.