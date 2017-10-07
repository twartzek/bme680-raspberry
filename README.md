# Introduction

This program serves as a working example to read the measurements from a BME680 via the raspberry pi. Actually I wanted to read out the sensor via python, but as the driver provided by Bosch is a C file, I created this small C program to communicate to the sensor. The compile program can then be called from python. 


# Usage guide
## Compiling the program
Download the driver for the BME680 from github and the file from this repository into the same directory.

As this program uses i2c-dev, check which bus is your I²C bus with `i2cdetect -y 1`. You might need to adapt the code according your I²C Bus in the line `g_i2cFid = open("/dev/i2c-1", O_RDWR);` to `g_i2cFid = open("/dev/i2c-0", O_RDWR);`


After this adaption you can compile the program with
`gcc bme680_main.c bme680.c -o bme680`


## Usage interface 
The program can be called with up to three parameters. However, be aware that no special input check is implemented.
1. `./bme680`: This will print three measurement results with the time of the measurement on the standard output stream. The delay between each measurement is 3 seconds.
2. `./bme680 -5 -10`: to be continued ...








