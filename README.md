# arduino-mk
gnu makefile for arduino using Arduino tool chain. supports Arduino 1.6.5+

I modified the makefile documented here: http://ed.am/dev/make/arduino-mk to work with Arduino 1.6.5 tool chain.  Authored by Tim Marston.

It required only a few modifications which can be seen by diff of second commit.  I've tagged the original as v1.6.0 and my changes as 1.6.5.  I have no way of knowing if any of it works on windows, nor do I care.      

## Installation
1. Install command-line build tools (needed for gnumake).  For mac, this means installing xcode build tools (https://developer.apple.com/downloads/)
2. put the ardunio-mk file somewhere.  I put mine in ~/projects/arduino-mk/
3. create a file named Make in the same directory as your .ino file.  Here is what my Makefile looks like in each of my projects.  It doesn't change unless I use a mega instead of uno:
```
# Makefile for uno
BOARD := uno
ARDUINODIR = /Applications/Arduino.app/Contents/Java
include ~/projects/arduino-mk/arduino.mk
```
_It's that easy!_

## Usage
```
cd yourproject dir
make install
```
will build and install source to board.  The makefile figures out which usb / com port the arduino is connected to .

```
make build
```
just compile the sources

```
make monitor
```
use screen to see and interact with arduino console. See `man screen` for more info.  Note, to exit from screen use Ctrl+a ctrl+\.  If I use any other way of closing it or unplug the arduino from the usb port before closing screen it messes up iterm2

## Shout out
Thank you Tim!


See also http://ed.am/dev/make/arduino-mk and the comment block at the top of arduino.mk file and for authors notes.


