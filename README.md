## RUPS (Raspbery PI UPS) custom componetnt for Home Assistant
Used to get data from UPS For Raspberry Pi

### UPS (With RTC & Coulometer) For Raspberry Pi 4B/3B+/3B
<details><summary>Description</summary>
<p>
This is a new version of UPS Board.It not only supports Raspberry Pi 4B but also adds type C output. It provides enough power for the Raspberry Pi to make your Raspberry Pi still work while moving, and its design is so smart that you can get rid of troubled of a mass wire. This UPS can provide you with the operation of replacing the battery yourself. This new UPS not only supports an independent RTC module, but also provides a coulomb counter.
You can obtain battery voltage and current information through I2C in the system. Combined with different programming methods, you can inherit the power information into the system. It is also convenient to detect the state of the battery, which can be detected and warned through the program. It can use most of the 18650 standard batteries and fully comply with the battery characteristics in terms of battery life. In addition, the power display provided on the circuit board is also very user-friendly. The illuminated LED light can quickly show the remain power and support the discharging while charging. You can directly connect to the external power supply for charging. At the same time, the Raspberry Pi will not be turned off.
<p>
</details>

[Official Site](https://wiki.52pi.com/index.php/UPS_%28With_RTC_%26_Coulometer%29_For_Raspberry_Pi_SKU:_EP-0118)

## Installation

### Install from HACS
Go to the hacs store and use the repo url `https://github.com/zvldz/rups`

Search the HACS Store for ```rups```

### Install manually
1. Clone this repo
2. Place the `custom_components/rups` folder into your `custom_components` folder

## Configuration

**Configuration variables:**
key | description | default
:--- | :--- | :---
**platform (Required)** | The platform name | rups
**name (Optional)** | Let you overwrite the name of the sensor | raspberry_ups
**monitored_variables (Optional)** | List of exposed variables | - bus_voltage
                                                                 - bus_current
                                                                 - power
                                                                 - shunt_voltage

# Sensor
The `rups` sensor platform allows you to get data from Raspberry PI UPS.

```yaml
# Example configuration.yaml entry
sensor:
  - platform: rups
    name: raspberry_ups
```

# Lovelace
```yaml
- type: entities
  entities:
    - sensor.raspberry_ups_bus_current
    - sensor.raspberry_ups_bus_voltage
    - sensor.raspberry_ups_power
    - sensor.raspberry_ups_shunt_voltage
```

# Automation
```yaml
```

