
Followed directions from [this forum post](http://www.raspberrypi.org/forums/viewtopic.php?f=32&t=22348) to make
smbus work with python3

## Before installation
```
sudo apt-get update
sudo apt-get install python3-dev
sudo apt-get install libi2c-dev i2c-tools
```

Follow [these directions](http://www.stuffaboutcode.com/2014/06/raspberry-pi-adxl345-accelerometer.html)
to unblacklist your I2C bus



README: py-smbus

To build:
	$ python setup.py build
On most GNU/Linux distributions, you'll need to install the python-devel
package for the build to succeed.

To install (will also build if necessary):
	$ python setup.py install

For general build/install help:
	$ python setup.py --help-commands

Frequently Answered Question:

Q: It's throwing exceptions, nothing works, what's wrong?

  A1: You need write permissions to the i2c-dev devices.  Try running as root.

  A2: Addresses in Linux/I2C are the most-sig 7 bits, right-justified.  E.g.
	if your device uses address 0xc0 to write and 0xc1 to read, then use
	address 0x60 with this module.

  A3: Some other kernel driver has claimed that I2C address.  Unload it first.

