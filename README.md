# Bosch IR transceiver
ESP32 IR transceiver for a Bosch EHP6.0-1 AA/I air to air heat pump.

**This is code for an ESP32 board with an IR sender and an IR receiver.**
The project is able to send correct IR signals to the heat pump and also receive IR signals from the original control.
The states are automatically updated independent of where the signal is sent from.
The IR-diods are placed in the vicinity of the heat pumps reciever.
The board and code is used with ESPHome in Home assistant.

To use the code, you have to modify wifi names, passwords etc to you needs.

```
api:
  encryption:
    key: "your_key"
  reboot_timeout: 15min

ota:
  - platform: esphome
    password: "your_password"


wifi:
  ssid: !secret wifi_ssid
  password: !secret wifi_password
  power_save_mode: none
  fast_connect: true
  reboot_timeout: 15min

  ap:
    ssid: "IR-Transceiver Fallback"
    password: "your_password"



  - platform: homeassistant
    name: "Your Temperature Sensor"
    entity_id: sensor.your_temperature_sensor
    id: temp_vardagsrum_temperature_bosch
    internal: false
    disabled_by_default: true
    device_class: temperature
    state_class: measurement
    unit_of_measurement: "°C"
```

<img width="755" height="2302" alt="llvp-vardagsrum local_" src="https://github.com/user-attachments/assets/17d3a3f1-c369-4f95-932b-9fb620d604cb" />




<img width="679" height="408" alt="image" src="https://github.com/user-attachments/assets/eccac5b3-0db4-4696-b0d0-ae068f49ff62" />

<img width="432" height="843" alt="image" src="https://github.com/user-attachments/assets/3d105e4e-fc8a-4264-93e3-584237a62570" />

<img width="673" height="655" alt="image" src="https://github.com/user-attachments/assets/6e612546-bf1f-4e46-ae57-f11b67aa90f3" />
