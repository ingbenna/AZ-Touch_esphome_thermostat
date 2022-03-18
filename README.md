# AZ-Touch_esphome_thermostat
Little thermostat based on AZ-Touch hardware and esphome.

I am not a writer or a designer and my english is so poor.
Please tell me any idea to improve this little project.

## First of all, photos!
### First page (homepage)
![002](https://user-images.githubusercontent.com/17341623/158959919-911d6e55-eff9-47e7-8729-20a49bc7d096.jpg)

From the upper left side we have:
- Gear icon: to switch to settings page
- Home: to set climate to "home" preset
- Away: to set climate to "away" preset
- On: to get the climate on
- Off: to get the climate off
- Auto/Man: to override or not the scheduled set of preset
- Internal temperature from "DHT22 AM2302" sensor
- Internal humidity from "DHT22 AM2302" sensor
- Internal pressure from "BMP280" sensor
- Up target temperature of 0.1 °C
- Current target temperature
- Down target temperature of 0.1 °C
- Current date and time from "DS3231" real time clock

### Second page (settings)
![001](https://user-images.githubusercontent.com/17341623/158959874-dc340779-1cda-43f8-a3c2-366e77508409.jpg)

From the upper left side we have:
- Back icon: to switch to homepage
- Home: to set climate to "home" preset
- Away: to set climate to "away" preset
- On: to get the climate on
- Off: to get the climate off
- WiFi/"X" icon: to check the status of wifi connection
- External temperature from OpenWeatherMap through HomeAssistant
- External humidity from OpenWeatherMap through HomeAssistant
- External pressure from OpenWeatherMap through HomeAssistant
- Up brightness of 20%
- Current brightness %
- Down brightness of 20%
- Current date and time from "DS3231" real time clock

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

The "DS3231" RTC is used to read the current date and time at the boot stage and to update them on sync with homeassistant.

### Display
The display is a "2.8" ILI9341" with a "XPT2046" resitive touch.
Attached to the backlight's turn on event we have a 60 seconds delay before turn it off: that's how we reached an auto turn off for the display backlight!

### Miscellanous
TODO:
- Explanation about sensors (hardware and owm)
