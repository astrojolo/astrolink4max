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

