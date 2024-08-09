# Temperature and Humidity(HTU21D Sensor) using an ESP32 that Broadcasts Data Over MQTT

### Description:
This program was written with the intent to measure temperature and humidity using an Espresif ESP32,
an HTU21D Temperature and Humidity sensor, and an optional power supply set to 3.3V. Alternatively, a
Micro USB connector can be used to power the board and sensor. The program sends data to the serial 
monitor (console output) and publishes [MQTT](https://mqtt.org/) messages using specific topics. A Node
Red program is subscribed to all the topics that are published and it also sends the messages to Home
Assistant.
 
### Parts List and Cost:
- [ESP32 Dev Module - $8.99](https://www.amazon.com/ESP-WROOM-32-Development-Microcontroller-Integrated-Compatible/dp/B07WCG1PLV/ref=sr_1_3?crid=3HPW3GPPHHIM3&dib=eyJ2IjoiMSJ9.sjPHOXDjh8AVtKhUaQxpfTsJ3k4lqRnMvkD37K6ng5VzinwMiIpsjFTshr77euDxMgyoptu8p8PzFvEWpxs40O3qLHpzCyHJ_KpOTdT0hLn_kZ5VvaaUsJZpMZ72DRqNjRW6rqDl4SjGiTwB9vDeKLDCDOqArCW1K2xaXXcrZTOxq8sxeWJr2FTZ0ll8o8OF8eiAo09CJ1BvkJmDdSup5OfI5wz17zlMgYynAIZk2Fs.pMx0hu62hox1BjN9oWdBfO2aGiNb33N04lTTgxFeisA&dib_tag=se&keywords=esp32%2Bdevkit%2Bv1&qid=1722836883&sprefix=esp32%2Bdevkit%2Caps%2C298&sr=8-3&th=1)
- [HTU21D Temp and Hum Sensor - $6.99 (Qty 3)](https://www.amazon.com/HiLetgo%C2%AE-Temperature-Humidity-1-5V-3-6V-Compatible/dp/B00XR7CR1I)
- [7-12VDC to 3.3/5V Power Supply, Jumper Wires, and breadboard - $11.99 (Optional)](https://www.amazon.com/Breadboard-Minidodoca-Alligator-Raspberry-Electronic/dp/B0CYLBY4HR/ref=sr_1_5?crid=36NHQ8XJ9KOC&dib=eyJ2IjoiMSJ9.46eVfNcBm7aKmhRLu1BFwPEeYiAerVPyF6tQEMtftR0dLdLMkKmbNDUu0H8oq5oDW6pdPSluE53eK7UwqUZ60FLFpqb4Ngpv45OkKyPDO-Uy2QKQLzfqN7RerbA1WNBG-qu66wxHIYPUVxiJnLcUwlIql47y3yRtmnVcIf_UBukh4bI2_di5vprYnUB32Ep7gyhvCa3-PtE5BzAD8XZqQ-iLnEu8O_8IzO_2DgxpzMg.4PphCUmAPyv6E9JG-rXhh1daSjYUc3haEXVms3uHslA&dib_tag=se&keywords=mini%2Bbreadboard%2Bpower%2Bsupply&qid=1722837301&sprefix=mini%2Bbrearboard%2Bpower%2Bsuppl%2Caps%2C161&sr=8-5&th=1)

### Setup:
- #### Wiring:
  * Note: The bread board rows are shorted together on the right(columns a-e) and left(columns f-j) sides.
  * ESP32 pressed into the bread board.
  * HTU21D pressed into the breadboard with all of the pins in the same column.
  * Power supply pressed into the (+) and (-) of the bread board. Note: If the power supply if connected on the "bottom" of the bread board, the polarity marked on the bread board will be incorrect.
  * If using the power supply to power the project:
  *   Jumper wire from (+) on the breadboard to the pin labeled VIN on the ESP32.
  *   Jumper wire from (-) on the breadboard to the pin labeled GND on the ESP32.
  * If using a USB cable to power the project:
  *   Jumper wire from the pin labeled 3V3 to "+" on the HTU sensor.
  *   Jumper wire from the pin lebeled GND to "-" on the HTU sensor.
  * Jumper wire from the pin labeled D21(SDA) on ESP to DA on the HTU sensor.
  * Jumper wire from the pin labeled D22(SCL) on ESP to CL on the HTU sensor.
