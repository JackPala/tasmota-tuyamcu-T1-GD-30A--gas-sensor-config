# Tasmota TuyaMCU T1-GD-30A Gas Sensor Config
Tasmota Configuration for the Tuya T1-GD-30A Gas Sensor Using TuyaMCU

Note - Before we begin I am not responsible for whatever problems or injuries come from the use of this config. Although the alarm MCU appears to work independently of the ESP8266 (Or TYWE3S), Occam's razer and Murphy's law still apply.



Limitations -

DPId Data is received as 00 as a positive detection of gas instead of 1, this means that we must manually define the value to be sent over MQTT instead of relaying the %value% variable in the event of gas detection.

This works - 
Rule1 ON TuyaReceived#dptype4id1 DO Publish stat/%topic%/GAS 1 ENDON

This does NOT work -
Rule1 ON TuyaReceived#dptype4id1 DO Publish stat/%topic%/GAS %value% ENDON
