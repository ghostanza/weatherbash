# weatherbash

This script connects to the Weather Underground API to bring weather forecasts to your command line.

## Basic Usage
* At the top of the script file there is a `loc` variable, this will be the location used by default when a location is not specified.
* You will need to use your own Weather Underground API key and set it as the `weather_key` value at the top of the script.
* The default display from calling `./weather` displays your default location, a brief message about the weather, the temperature, the "feels like" temperature, and the humidity.`

```
$  ./weather

===== Boston MA =====
Light Rain
58.3 F (14.6 C)
Feels Like 58.3deg
Humidity: 85%
```


## Options
#### `-s` - Summary
This is the default setting ( you do not need to use the flag )

---

#### `-c` - Complete Forecast
This will give you a 3-day/night forecast for the location
_Example:_
```
$   ./weather -c


		----- FULL FORECAST FOR BOSTON -----

= S A T U R D A Y  =======================
Mainly sunny. High 68F. Winds NNW at 10 to 15 mph.

= S A T U R D A Y   N I G H T  =======================
Clear skies. Low 44F. Winds NW at 10 to 15 mph.

= S U N D A Y  =======================
Sunny. High 64F. Winds NW at 10 to 20 mph.

= S U N D A Y   N I G H T  =======================
Clear. Low 41F. Winds NW at 5 to 10 mph.

= M O N D A Y  =======================
Sunshine and some clouds. High near 65F. Winds SSW at 5 to 10 mph.

= M O N D A Y   N I G H T  =======================
Partly cloudy in the evening. Increasing clouds with periods of showers after midnight. Low 51F. Winds S at 10 to 15 mph. Chance of rain 60%.

= T U E S D A Y  =======================
Rain showers early with some sunshine later in the day. High 69F. Winds SW at 10 to 20 mph. Chance of rain 50%.

= T U E S D A Y   N I G H T  =======================
A few clouds from time to time. Low 54F. Winds SW at 10 to 15 mph.
```

---

#### `-sset` - The time of today's sunset
_Example:_
```
$   ./weather -sset

   Sunset today is at 6:37PM local time

```

---

#### `-alerts` - Weather alerts in your area
_Example:_
```
$    ./weather -alerts

   There are currently no weather alerts for your area.
```

---

#### `-rain` - Chance of Rain (percentage)
_Example:_
```
$    ./weather -rain

     ======= Chance of Rain in Your Area =======
     Today: 80%	  		    Tonight: 70%
```

---

## Helpers/Modifiers

*_The Helpers/Modifiers are signified by a double-dash (`--`) argument whereas the single-dash (`-`) arguments refer to the weather/display type_* 

### `--help` - Display the documentation

---

### Custom Location
If you want to check the weather for a location other than your default location, there are two options.

#### Zip Code Flag
By calling the script with the `--z` argument, you will be prompted to put in a zip code which will be used in the call.
_Example:_
```
$   ./weather --z
Enter Zip Code:
> 02108

===== Boston MA =====
Light Rain
58.3 F (14.6 C)
Feels Like 58.3deg
Humidity 85%
```

#### City/State Flag
By calling the script with the `--t` argument, you will be prompted to enter a town name and then a state or country abbreviation.
_Example:_
```
$    ./weather --t
Enter Town/City Name;
> San Francisco
Enter Two-Letter State (or country, if not in US) Abbreviation:
> CA

===== San Francisco CA =====
Mostly Sunny
75 F (23.8 C)
Feels like 75deg
Humidity: 67%
```

---

#### `--alias [name]` - Create alias
This command creates an alias for the script in your `.bash_profile`. It takes an optional `name` - the default name it uses is `weather`.
_Example:_
```
$   ./weather --alias myweather

    Successfully created an alias named 'myweather' to bash_profile
    Now just run 'source ~/.bash_profile' to make it official!
```

## Full Configuration
You are allowed to combine one location argument with one weather type argument
```
./weather -c --t

./weather --t -c

./weather -rain --z

etc etc etc...
```
