# Satellite ring range and count calculator

This tool allows to calculate the maximum range from the link budget optimal altitude (higher) and number of satellite (fewer) to do a complete ring around a target body.

## Lib

This tool require jupyter and sympy installed, on any good system do :
```sh
pip3 install sympy jupyter
```
I've not tested it with python2 ([EOL](https://www.python.org/dev/peps/pep-0373/)).

## Defaults

By default it simulate the earth with a clearence of 100km (that too big but in this compenssate the relief) and lora emiter and receiver (for a fact, lora for space to space transmission doesn't seems like the best application).

## Known bad assumptions

For simplicity reasons some bad assumptions are made, here is the list of the most important one :

- Infinitly precise float, value are not perfectly acurate but that good enough for me.
- Earth is a perfect 6371km radius sphere, wrong due to earth rotation making it fatter at the equator, to accomodate that add 7km to clearence radius (difference beetween mean level and mean equatorial level).
- Earth is a perfect sphere, obviously wrong due to relief, to accomodate use a slightly bigger clearance radius.
- Link budget is perfectly calculated, if you have a link budget of 0.02 dbm your connection is not gonna work reliably, to accomodate that may substract 5 to 8 dbm to your link budget.
- Line of site is perfect, dust, orbital debris, ... remove a bit of dbm from your link budget (1 dbm ? (the effect is probably less)).
- Light doesn't bend, light might bend due to Diffraction but if this effect became unnegligeable your clearence is probably too small.
- Light travel in a straight line, wrong due to general relativity, effects are very probably negligeable.
