# esp8266-beacon
This is a simple PCB that combines an ESP8266-01 and a buck voltage converter. The ESP is expected to be socketed and lays over the voltage converter.
The voltage converter is an adjustable device set for 3.3V.
The ESPHome code simply connects to the local WiFi when in range.
The project came about because I connected my garage door opener to Alexa and I wanted to not let the doors open if the associated vehicle was not in WiFi range.

In Home Assistant:
I have an ESP01 in my Jeep that I use for presence.
If the ESP connects, then the Jeep is present.
I use a binary helper that I turn on on the dashboard that is basically a semaphore to tell the ESP that I want it to not go to sleep. The test_ota script in the code below is where this is tested when the ESP boots.

The sequence is:
1. Turn on OTA mode.
2. Wait for the sleep period to end, then the ESP reboots and will not go to sleep.
3. Perform my OTA upload.
4. Turn off the OTA mode.
5. Press "Restart" on the dashboard to reboot the ESP.

![Home Assistant Dashboard]([images/jeep.jpg) "Home Assistnat Dashboard")
