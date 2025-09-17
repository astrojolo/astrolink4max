![AstroLink 4 MAX Banner](https://shop.astrojolo.com/wp-content/uploads/sites/2/2025/07/astrolink-max-banner-2025.jpg)

# AstroLink 4 MAX  

![ASCOM Compatible](https://img.shields.io/badge/ASCOM-Compatible-blue)  
![USB 3 Hub](https://img.shields.io/badge/USB-3%20Hub-green)  
![Power Outputs](https://img.shields.io/badge/Power-12V-orange)  
![Dew Control](https://img.shields.io/badge/Dew%20Control-PWM-red)  
![Colors](https://img.shields.io/badge/Colors-Black%20%7C%20Graphite%20%7C%20Cherry%20Red-lightgrey)  

---

## Overview  
AstroLink 4 MAX is a multifunctional controller designed to simplify astrophotography setups by unifying power management, motor control, environmental sensing, and expansion options. It offers advanced features while remaining compact and easy to integrate with popular software platforms.  

---

## 🔑 Key Features  
- **Integrated USB Hub**  
  - 3-port active USB 3 hub with EMI and overcurrent protection.  

- **Power Distribution**  
  - 3 switchable 12V DC outputs.  
  - 1 permanent 12V output.  
  - 1 regulated 3–10V DC output for accessories.  

- **Dew & Cooling Control**  
  - 2 independent PWM channels (0–100%).  

- **Motor Focuser Control**  
  - Supports unipolar and bipolar stepper motors.  
  - Microstepping support (1/8, 1/32, etc.).  
  - Temperature-based compensation and position memory.  

- **Environmental Sensing**  
  - Temperature, humidity, sky temperature/cloud coverage, and sky brightness.  
  - Monitors input voltage, current draw, and energy usage.  

- **Safety & Expansion**  
  - Protection against overvoltage, overcurrent, and low battery.  
  - AUX port for external modules and future expansions.  

- **Software Integration**  
  - **ASCOM drivers**: Focuser, Switch, ObservingConditions, SafetyMonitor.  
  - **INDI driver** planned for release in Q3 2025.  

- **Available Colors**: Black, Graphite, Cherry Red.  


## Device
https://shop.astrojolo.com/product-detail-pages/astrolink-4-max/


# AstroLink 4 MAX driver installation
## Requirements
* INDI http://indilib.org/download.html


### Required packages
```
sudo apt update
sudo apt install git build-essential cmake libindi-dev
```

### INDI driver installation
```
git clone https://github.com/astrojolo/astrolink4max
cd astrolink4max
mkdir build && cd build
cmake -DCMAKE_INSTALL_PREFIX=/usr ..
make
```
You can install the drivers by running:
```
sudo make install
```
After these steps AstroLink 4 MAX driver will be visible in the Aux devices lists under **Astrojolo** group.