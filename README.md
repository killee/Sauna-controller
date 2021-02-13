# Sauna-controller
Sauna Controller with esp8266 and [ESPHome](https://esphome.io/) for a integration in [Home Assistant](https://www.home-assistant.io/) 
There are many cases to automate a Sauna ;-).


In my case I've build up the hole Sauna. Nothing existed. So I desided to build up also the controller.
The big advantage you get for about 60€ a sauna controller that is awesome!
To start from nothing this one is a bit different.

The hole controller is build up from scratch. 
The integreation is done with Home Assistant. The controller itself is build around the awesome [ESPHome](https://esphome.io/).

# features
- real PID controller
- calculate the power and energy
- customizable
- no cloud
- remote access
- expandable
- cheap
- reliable
- easy to build
- easy to use
- 


# components
There are only a few components needed:

1. **The brain of the Sauna Controller** A Wemos D1 a ESP8266 microcontroller running ESPHome

2. **temperature sensors** at least one DS18B20 to messure the temperature in the Sauna. In my setup there are 4 DS18B20. So I'm able to messure the temperature in different places (at the top of the Sauna, at a bench, in the Sauna Controller and in the fancy Sauna lamp)

3. **Thermal fuse** a very important thing. If something goes wrong and the heater heats the termal fuse burns and switch off the heater. Its a very simple part and cuts the voltage vor the high current switches

4. **a high current/voltage switch to heat the sauna with the heater** I chouce a SSR relay in like 3 SSR-40DA. A SSR relay is wear-free. It is easy posibility to bild up a PID controller.
5. **optional door sensor** I've a reed contact in the sauna door. If the door is open the controller can switch off the sauna. The controller reset also a timer when the door is opend. Thats cool if you use the sauna the hole day and the normal timer will switch off the sauna.
6. **optional more sensors** I use different other sensors to messure the temperature in the room, between the sauna wall and the room wall including humidy. 
7. **Sauna lamp** the controller with the brain is a bit bored with only the PID controller. So another task for the controller is to drive WS2812b LEDs for the sauna lamp. It can do funny effects.
8. **junction box cabels and so on** there are many other smal things

# Software
The sauna controller has the hole UI in the [Home Assistant](https://www.home-assistant.io/). In my case this is very good, so the kits can not switch the sauna on by playing in the sauna room.
The software runs on the controller is build with the awesome [ESPHome](https://esphome.io/). The hole configuration is in the sauna_controller.yaml. It is easy customizable to another setup.
In the Home Assistant frontend you can the set temperature switch the sauna on and get a notification if the sauna is ready.
The controller itself controlls the temperature without Home Assistant.
Messure the temperature
calculate the needed power
controlls the heater
switch off the sauna if the door is to long open
calculate the power and the energy you need for the sauna
...


# things to do
There is no timer yet to get the time like a sand clock. A sand clock with WS2812 and the door sensor would be nice.
Find more things to automate, switch off the room climate if the sauna is running.

# background
To control a Sauna its simple...
Messure the temperatur and switch on and off the oven. Thats it.

The temperature is messured with a DS18B20. The software runs on a ESP8266 in this case a Wemos D1. The oven is switched by 3 SSR-40DA. With a climate PID regulator the temperature in the Sauna is 

# Inspiration
This projekt was heavily inspired by: 
https://github.com/bastiaanterhorst/sauna-automation
https://github.com/quicklywilliam/saunakit

Very nice projekts!

