# Home Assistant Monitor
For a long time I have been trying to make Home Assistant Cast for my own setup. Unfortunately I never got it set up to my satisfaction. My camera's don't seem to be compatible, and custom lovelace cards won't render. Another disadvantage is the total lack of local control of what is on the display when using a Chromecast.

Enter Home Assistant Monitor. The concept is simple: replace the Chromecast with a a kiosk-browser on an RPI Zero W; or the Google Nest Hub with an RPI4 with touch display. This opens the door to a lot more interaction with the user / display.

## Main functions
* Display the Home Assistant user interface on a monitor (TV or other)
* Allow local control over touch, CEC from TV, (wireless) keyboard/mouse or infrared
## Planned functions
* Local webserver to manage setup of the device
* Discovery of Home Assistant over Bonjour / Avahi
* REST API (or other) for direct control of the display functions (which view to show etc)
* Buttons on the remote can trigger Home Assistant automations
* Home Assistant Integration to automatically set up controls of the monitor
* Set up wireless through python wireless library
* Filter mouse /keyboard input through evdev
* Web configuration using bottle

## Current Status
- [X] Right now I'm experimenting with some Bash scripts to implement basic functionality. Main purpose is to discover if the concept is usable and what the limitations are.
- [ ] Move the functions to python
- [ ] Set up "light" version of Raspbian without a full desktop
- [ ] Add webserver for configuration of the RPI

## Installation
- Chromium kiosk browser using https://die-antwort.eu/techblog/2017-12-setup-raspberry-pi-for-kiosk-mode/
- CEC control using https://github.com/trainman419/python-cec
- Install pip `sudo apt install python3-pip`
- Set up virtualenv https://uoa-eresearch.github.io/eresearch-cookbook/recipe/2014/11/26/python-virtual-env/ (but use `sudo` in the install step)
- add pyautogui https://pypi.org/project/PyAutoGUI/
- add cec https://github.com/trainman419/python-cec/tree/b585a99a1ed5eae7c7957a8aada7a6b6e951d452
- execute vcgencmd force_audio hdmi 1 to avoid audio cuts when used
- install audio

## Configuration
- /etc/xdg/openbox/autostart https://github.com/tnagels/home-assistant-monitor/blob/main/autostart
- /etc/X11/xorg.conf https://github.com/tnagels/home-assistant-monitor/blob/main/xorg.conf
