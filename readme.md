# Running COBOL code on Arduino with Meson

Who says COBOL is only suitable for boring bank, insurance and
payroll applications?  This project demonstrates how you can use it
to do embedded code on an Arduino microcontroller.

## Requirements

 - [Meson](http://mesonbuild.com)
 - [GNU COBOL](http://open-cobol.sourceforge.net/)
 - [Arduino toolchain](http://www.arduino.org/)

## Compile + upload

    mkdir build
    meson --cross-file arduino_uno_cross.txt build
    cd build
    ninja ardup

## Other things of note

The scripts assume Linux and that your Arduino is in `/dev/ttyACM0`.

The code was tested with the GNU Cobol that was in Ubuntu repos at the
time when the project was created. If GNU Cobol has changed its
internals this project might fail to compile. The reason is that this
application has its own, extremely minimal implementation of the GNU
Cobol runtime. It can't use the standard version because of space
constraints.

## Going deeper

How the system works is explained in detail in [this blog
post](http://nibblestew.blogspot.com/2016/06/running-cobol-on-arduino-using-meson.html).
