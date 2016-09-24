# weatherbash

This script connects to the Weather Underground API to bring weather forecasts to your command line.

## Basic Usage
* The script has a default `loc` variable, this will be used by default.
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
