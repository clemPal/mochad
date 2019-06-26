Domoticz to Marmitek Gateway
============================

A Ubigate Plugin, to read data from MQTT topic on the same host provided by Domoticz and transfer them to Ubismart in the same format as Marmitek.

It handles Z-Wave sensors: MultiSensor 6 (particularly Motion sensor), Contact sensor

# Problems:

## Sensors environment measures doubling up (Temperature and Humidity)

When using a MultiSensor to send signal for temperature and humidity measurements, the mqtt messages are doubled. The cause is that both temperature and humidity send values for both measurements. Sending just one of the two is not a soltuion though because in that case both temperature and humidity will be sent via mqtt but only one value will be updated the other will be constant and equal to last updated value.
