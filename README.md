# weatherbash

This script connects to the Weather Underground API to bring weather forecasts to your command line.

## Basic Usage
* The script has a default `loc` variable, this will be used by default.
* You will need to use your own Weather Underground API key and set it as the `weather_key` value at the top of the script.
* The default display from calling `./weather` displays your location, a brief message about the weather, the temperature, and the "feels like" temperature

```
$  ./weather

===== Boston MA =====
Light Rain
58.3 F (14.6 C)
Feels Like 58.3deg
```

## Custom Location
There are two different ways you can specify what location you'd like to use on the fly (aside from changing the default location in the script itself).

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

----- FULL FORECAST FOR SAN FRANCISCO -----
===== Friday =====
Partly cloudy. Lows overnight in the mid 50s.

===== Friday Night =====
Partly cloudy skies. Low around 55F. Winds NW at 10 to 20 mph.

===== Saturday =====
A mainly sunny sky. High 73F. Winds NNE at 5 to 10 mph becoming W and increasing to 10 to 20 mph.

===== Saturday Night =====
Clear skies. Low near 55F. Winds NNE at 10 to 15 mph.

===== Sunday =====
Mainly sunny. High 82F. Winds NNE at 10 to 20 mph.

===== Sunday Night =====
A mostly clear sky. Low around 55F. Winds NW at 10 to 15 mph.

===== Monday ======
Sunny. High 82F. NE winds shifting to WNW at 10 to 15mph.

===== Monday Night =====
A mostly clear sky. Low around 55F. Winds W at 5 to 10 mph.
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

