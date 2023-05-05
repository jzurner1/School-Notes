An asynchronous transmission is a transmission that does not require a clock signal but instad adds extra bits to track the beginning and end of the data.

# Vocab
There are a number of terms related to asynchronous transmission that are important to know:

### Baud
The number of times an analog signal changes in one second, sometimes used as a unit for modem speed. With modern modems, it is better to specify speed using bits per second.

### Bits per second
Measurement used to describe the transmission speed of serial devices and ports. The application software must match the serial device or serial port's bits per second rate.

### RS232C
A standard approved by the EIA for the serial port used in a computer. Devices that use this standard are often called RS232 serial devices.

### Start bit
The bit used in asynchronous transmissions to signal the start of the data

### Stop bit
The bit used in asynchronous transmissions to signal the end of the data

### UART
Univeral asynchronous receiver/transmitter, a chip on the motherboard for an integrated serial port or on the adapter of an internal modem. Converts a data byte into a serial data stream of 1's and 0's for transmission. Also receives the bit stream and stores data until the processor can accept the data.