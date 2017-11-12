# Memory, Data Types, And Serial Communication


How to represent information digitally

    Use a light bulb to represent whether zero, one, two, or three students are in a room
        You could use 4 different brightness levels, including full on and full off
    What about 10 students? 100?
        It would be hard to tell the difference between that many different light levels
    That’s analog. Try digital:
        Use multiple bulbs and a code
        Each bulb is either on or off, never in between (binary: one of two values)
        4 bulbs let us count up to 15
        8 bulbs let us count up to 255
    8 bulbs turns out to be a pretty good compromise between the amount of information and the number of bulbs
        One bulb = 1 binary digit = 1 bit
        Eight bulbs = 8 bits = 1 byte
    Arduino and many other microcontrollers (and early computers) were built around an 8 bit bus (sort of like an 8 lane highway)
    Examples of ways to represent information with 8 bit
        Letters using the [ASCII code](http://www.asciitable.com/)
        Positive and [negative](https://en.wikipedia.org/wiki/Two%27s_complement) numbers. Also [floating point](https://www3.ntu.edu.sg/home/ehchua/programming/java/datarepresentation.html) and others

ATmega328: The microcontroller used in the Arduino Uno

    ATmega328 microcontroller [data sheet](http://www.atmel.com/images/Atmel-8271-8-bit-AVR-Microcontroller-ATmega48A-48PA-88A-88PA-168A-168PA-328-328P_datasheet_Complete.pdf)
        Block diagram on pg 6
        AVR diagram on pg 9
        What are registers? Can be either
            A generic piece of memory internal to the processor
            A very specific piece of memory that controls the behavior of some of the hardware
        What are I/O ports?
            Pins can be addressed individually (as bits) or in groups of 8 (as bytes)
            Find the ports in the datasheet (table of contents is at the end)
                pg 75
        IC pinout on pg 3

How does Arduino code accomplish what’s in the datasheet?

    Arduino Uno schematic (arduino.cc – products – Uno)
        How does Arduino manipulate the registers, e.g. how does pinMode work?
            ~/arduino-1.6.8/hardware/arduino/avr/cores/arduino/wiring_digital.c

Serial vs. parallel

    Parallel modes of transmitting information
        Moves lots of information quickly
        Takes lots of wires
    Alternative?
        Serial
            [Asynchronous](https://learn.sparkfun.com/tutorials/serial-communication)
            [SPI](https://learn.sparkfun.com/tutorials/serial-peripheral-interface-spi)
            [I2C](https://learn.sparkfun.com/tutorials/i2c)
    Arduino pins with special functionality

Related topics :

    Digital logic slides
    Shift registers as UARTs
    Interrupts
    Timers
    Binary number system
