# Automation - Chromecast / Chromecast Audio

Example config.json:

```
    "accessories": [
        {
            "accessory": "AutomationChromecast",
            "name": "Test",
            "chromecastDeviceName": "<The device Name of your Chromecast>"
        }  
    ]

```

This accessory will create a switch linked with the status of a Chromecast or Chromecast Audio device.
It will also create a Motion Sensor, to trigger automations.


When you stream some audio/video to the Chromecast / Chromecast Audio, the switch turns on and the Sensor detects movement. Stop the streaming will turn the switch off and the sensor will stop detecting movements.

Turning On the switch will play the currently casted stream. Turning Off the switch will stop the stream.

Please note: the `chromecastDeviceName` has to be the name of the device as set in the Google Home app (E.g. "Living Room", case insensitive). This plugin will use Bonjour/mdns to detect the IP address of the Chromecast.

This project as been largely inspired by the work of [@robertherber](https://bitbucket.org/robertherber/homebridge-chromecast/src)

# Example: Dim the lights when I stream some video to my Chromecast
1. Create an accessory in Homebridge (code example at the top of this readme)
2. Create a new automation in iOS Home/HomeKit: when the Motion Sensor detects movement, trigger a scene of your choice (e.g. "Movie lights")
3. Start streaming to the Chromecast. The Motion Sensor will detect a movement, triggering the scene