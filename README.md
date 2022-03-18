# AZ-Touch_esphome_thermostat
Little thermostat based on AZ-Touch hardware and esphome.

I am not a writer or a designer and my english is so poor.
Please tell me any idea to improve this little project.

## First of all, photos!
### First page (homepage)
![002](https://user-images.githubusercontent.com/17341623/158959919-911d6e55-eff9-47e7-8729-20a49bc7d096.jpg)

### Second page (settings)
![001](https://user-images.githubusercontent.com/17341623/158959874-dc340779-1cda-43f8-a3c2-366e77508409.jpg)

## The hardware
The main hardware is based on the "AZ-Touch ESP" kit with the "ESP32 DEV KIT C", "2.8" ILI9341" display and "XPT2046" resitive touch.
Then I added the "DS3231" real time clock, "BMP280" sensor (used for pressure), "DHT22 AM2302" sensor (used for temperature and humidity) and a simple relay.

## Then, features!
### Climate
The project have a climate entity, connected to the relay. It can be used for command an heating boiler.

### Scheduler
The project contains an internal scheduler that works even without any connection (neither with internet, neither with homeassistant).
It is based on the entity time, connected with the internal RTC clock and apply some preset to the climate entity.
I know that intervals are configurable only through esphome yaml, I desire to make this configuration dinamic with the possibility of modification through frontend but for now seems to be little complex.

We also have a virtual button in the homepage (under the gear icon) to override eventually settings applied by the scheduler.

### Miscellanous
TODO:
- RTC read time on boot and write time on ha sync
- Explanation of pages and virtual buttons
- Explanation about sensors (hardware and owm)
- Auto turn off backlight
