GardenPi
=================

Autowatering of my garden via Raspberry Pi

More info:

[blog post about setting up your own GardenPi](https://spin.atomicobject.com/2014/06/28/raspberry-pi-gardening)


GardenPi: Garden Care with Raspberry Pi
By Shawn Anderson | Published: June 28, 2014
garden_pi_prototype
Like any good “lazy programmer,” I’m always looking for ways to automate. This spring’s project: monitoring and watering my garden. I had a wifi-enabled Raspberry Pi laying around and decided to put it to good use. For this project I wanted to do better than just a glorified timer. The goal: An automated watering system that can use the weather forecast, soil, light, and temperature sensors to keep my garden looking great all summer.

Phase 1: Timer and Forecast-Based Watering
I’ve written a simple script that wakes up at 10PM, determines the likelihood of rain, and waters accordingly. The script looks up the forecast using the Forecast.io API. If there is less than a 50% chance of rain, the GardenPi will water for a short duration.

Future phases (already underway) will include sensors for temperature, soil moisture, light, and humidity. Based on that information, the GardenPi will be able to make better watering decisions. The sensor data could be made available via an onboard website or mobile application. Better sensors, form factor, time lapse, and user interface are all things that I’ll be looking at for future versions.

I’ve learned a lot in the last few weeks from building this project — a little bit more about basic electronics, how to solder, how to draw up schematics, and the joy of building actual gizmos that serve a purpose. I’ve also learned that I’m not the only one doing this kind of project with the Raspberry Pi; I’ve included links to other projects at the end of this post.

Required Parts (approx. cost ~$85)
Raspberry Pi
USB Wifi Dongle
SD Card
Soaker / Drip hose throughout the garden
Solenoid for turning on the soaker hose
A female hose swivel adapter to connect your garden hose to the solenoid
Relay for switching 12V power
12V / Raspberry Pi power supplies
Assorted electronics (breadboard, resistors, wires, LED)
High tech weather resistant case (aka medium sized Tupperware container)
Steps
Install Raspbian and configure WiFi access.
Install Ruby for root user.
Run gem install god.
Pull the garden_pi_waterer repository && bundle install to install dependencies.
Modify the parameters (forecast.io API key, timing info, etc.) in environment.rb.
Build out breakout board (see schematic below).
Connect the solenoid between water source and soaker hose, taking note of the directional arrow on the solenoid and using the adapter to connect the male end of your garden hose to the input on the solenoid.
Power up the Pi and your 12V power supply.
Install install/init.d to /etc/init.d/god and follow instructions in that file
Install god.conf to /home/pi
Restart and enjoy.
Results
I’ve watered my garden with a Raspberry Pi. Success. There is a lot of room for improvement, and I’m looking forward to extending the GardenPi’s capabilities.

Schematic
basic_watering_schematic
