# 🐍 Python cheatsheet

Just the basics to get coding using MicroPython on the BBC microbit [python.microbit.org](https://python.microbit.org)

[PDF copy for print](https://microbitcheatsheet.mrkn.us/cheatsheet.pdf)

## Features

### import microbit library

Import every class, function and variable

`from microbit import *`

Import only the display class

`from microbit import display`

Import the microbit library

`import microbit`



### [Buttons](https://microbit-micropython.readthedocs.io/en/latest/tutorials/buttons.html)

Was a button pressed?

`buttona.was_pressed()`

Is a button currently pressed?

`buttonb.is_pressed()`



### [Accelerometer](https://microbit-micropython.readthedocs.io/en/latest/accelerometer.html)

Gestures: `up`, `down`, `left`, `right`, `face up`, `face down`, `freefall`, `3g`, `6g`, `8g`, `shake`

Was the micro:bit shaken?

`accelerometer.was_gesture("shake")`

Is the micro:bit currently falling?

`accelerometer.is_gesture("freefall")`

What is the value of the accellerometer x axis?

`accelerometer.get_x()`



### [ Compass](https://microbit-micropython.readthedocs.io/en/latest/compass.html)

Run the compass calibration routine

`compass.calibrate()`

What is the compass heading from 0 - 360 degrees?

`compass.heading()`

What is the field strength on the y axis in nano teslas?

`compass.get_y()`



### [Music](https://microbit-micropython.readthedocs.io/en/latest/music.html)

Play happy birthday

`music.play(music.BIRTHDAY)`

Create an array called `tune` of "NOTE OCTAVE:DURATION" then play it.

```python
tune = ["C4:4", "D4:4", "E4:4", "C4:4", "C4:4", "D4:4", "E4:4", "C4:4",
        "E4:4", "F4:4", "G4:8", "E4:4", "F4:4", "G4:8"]
music.play(tune)
```

Play a pitch (Frequency(Hz), Duration(ticks))

`music.pitch(440, 6)`

Set the tempo

`music.set_tempo(ticks=4, bpm=120)`



### [Radio](https://microbit-micropython.readthedocs.io/en/latest/tutorials/radio.html)

Import the radio module

`import radio`

Turn the radio on or off

`radio.on()`

Send a string via radio

`radio.send('duck')`

Return whatever radio message was received

`radio.receive()`



### [Input/Output pins](https://microbit-micropython.readthedocs.io/en/latest/pin.html)

Is a pin currently being touched?

`pin0.is_touched()`

Return the current value on a pin

`pin1.read_analog()`

Write a value to a pin

`pin2.write-digital(1)`



### LED Display (text, [image](https://microbit-micropython.readthedocs.io/en/latest/image.html))

Images: `HEART`, `HEART_SMALL`, `HAPPY`, `SMILE`, `SAD`,`CONFUSED`, `ANGRY`, `ASLEEP`, `SURPRISED`, `SILLY`, `FABULOUS`, `MEH`, `YES`, `NO`, `CLOCK12`, `CLOCK11`, `CLOCK10`, `CLOCK9`, `CLOCK8`, `CLOCK7`, `CLOCK6`, `CLOCK5`, `CLOCK4`, `CLOCK3`, `CLOCK2`, `CLOCK1`, `ARROW_N`, `ARROW_NE`, `ARROW_E`, `ARROW_SE`, `ARROW_S`, `ARROW_SW`, `ARROW_W`, `ARROW_NW`, `TRIANGLE`, `TRIANGLE_LEFT`, `CHESSBOARD`, `DIAMOND`, `DIAMOND_SMALL`, `SQUARE`, `SQUARE_SMALL`, `RABBIT`, `COW`, `MUSIC_CROTCHET`, `MUSIC_QUAVER`, `MUSIC_QUAVERS`, `PITCHFORK`, `XMAS`, `PACMAN`, `TARGET`, `TSHIRT`, `ROLLERSKATE`, `DUCK`, `HOUSE`, `TORTOISE`, `BUTTERFLY`, `STICKFIGURE`, `GHOST`, `SWORD`, `GIRAFFE`, `SKULL`, `UMBRELLA`, `SNAKE`

Scroll a string across the display

`display.scroll('hello world')`

Show an image on the display

`display.show(Image.DUCK)`

Return the light level from the display

`display.read_light_level()`


### [Temperature](https://microbit-micropython.readthedocs.io/en/latest/microbit.html?highlight=temp#microbit.temperature)

What is the current temperature?

`temperature()`



### [Neopixels](https://microbit-micropython.readthedocs.io/en/latest/pin.html)

Import the Neopixel module

`import neopixel`

Initialise a strip of Neopixels (pin, number of Neopixels)

`neopixel.Neopixel(pin0, 10)`

Send the current colour data to the Neopixels

`neopixel.Neopixel.show()`



### [Pause](https://microbit-micropython.readthedocs.io/en/latest/microbit.html#microbit.sleep)

Sleep for a number of milliseconds(ms)

`sleep(500)`

 

## Coding concepts

### Variables

Set the compass heading to a variable

`direction = compass.heading()`

Set the received radio message to a variable

`incoming = radio.receive()`



### Loops

```python
while True:
        display.show(Image.HEART)
        sleep(10)
        display.show(Image.HEART_SMALL)
        sleep(10)
```



### Conditions

```python
if accelerometer.was_gesture("shake"):
        display.scroll('shake')
        elif accelerometer.was_gesture("face down"):
        display.show(Image.HAPPY)
else:
        display.clear()
```

### MicroPython Easter Eggs

`import love()`


