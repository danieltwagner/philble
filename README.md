# philble
Python 3 library to control Philips Hue lights over Bluetooth Low Energy (BLE). Uses
the` Adafruit_Bluefruit_LE` library to issue Bluetooth commands from either Linux or macOS.

**Minimal working example: See `example.py`**

## API
See `philble/client.py` for commands available and mapping on to the BLE interface.

```python
import philble.clint
client = philble.client.Client(device)
```

* `power(False | True)`
* `brightness(0..255)`
* `temperature(153...454)`: Color temperature *decreases* as index increases, for some reason.
* `color(hex string)`

#
## lightcom
A small demo, providing an `IPython` REPL for controlling light fixtures. Modify
`config.py` to provide names for your lights. The light client objects are available
in a global variable called `l`.

## TODO:
* [ ] Figure out which sleeps are due to BLE library oddness and which are due to my sloppy implementation.
* [ ] Read current values for these parameters.
* [ ] Fully understand color code.
* [ ] Provide HSL input for colors - probably easier to reason about for lighting.
* [ ] Save state after lamp power-cycle.
* [ ] Create demo to activate lamps relative to sunrise/sunset.
* [ ] Enable client to be installed in a sane manner.
