# Light Control Using Kasa Smart Plug and Node-Red

![alt text](https://github.com/withabubaker/Light-Control/blob/master/img/IMG_JPG.jpeg)


## Project Goals:

- Schedule decoration light turn on/off time using Python code.
- Convert Python script to a service that's running in the background on Raspberry pi.
- Visualize/dashboard the light status using Node-Red, green if the light is on, and red if the light is off.


## Libraries & Tools & Hardware:

1. Python 3.7.3
2. [Kasa Smart Plug](https://www.kasasmart.com/us/products/smart-plugs)
3. MQTT
4. Raspberry Pi 4
6. Decoration light

## Setup Linux Service to Run Python app in the Background

1. Create a new service file
```bash
sudo nano /etc/systemd/system/ControlKasaSmartPlug.service
```

2. add the following to the file (update the name and location as required)

```bash
[Unit]
Description=Kasa Smart Plug Control Service
After=network.target

[Service]
ExecStart=/home/pi/bin/python /home/pi/ControlKasaPlug.py
WorkingDirectory=/home/pi/
StandardOutput=inherit
StandardError=inherit
Restart=always
User=pi


[Install]
WantedBy=multi-user.target
```

## Files:
- ***Node-Red JSON Flow.json***: flow nodes for visualizing/dashboard the light status.
