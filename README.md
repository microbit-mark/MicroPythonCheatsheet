# Python Editor cheatsheet

Just the basics to get coding using MicroPython on the microbit [python.microbit.org](https://python.microbit.org)


## Features

### import microbit library

`from microbit import *`

`from microbit import display`

`import microbit`



### Buttons

`buttona.was_pressed()`

`buttonb.is_pressed()`



### [Accelerometer](https://microbit-micropython.readthedocs.io/en/latest/accelerometer.html)

`accelerometer.was_gesture("shake")`

`accelerometer.is_gesture("freefall")`

`accelerometer.get_x()`



### [ Compass](https://microbit-micropython.readthedocs.io/en/latest/compass.html)

`compass.calibrate()`

`compass.heading()`

`compass.get_y()`



### [Music](https://microbit-micropython.readthedocs.io/en/latest/music.html)

`music.play(music.BIRTHDAY)`

```python
tune = ["C4:4", "D4:4", "E4:4", "C4:4", "C4:4", "D4:4", "E4:4", "C4:4",
        "E4:4", "F4:4", "G4:8", "E4:4", "F4:4", "G4:8"]
music.play(tune)
```

`music.pitch(440, 6)`

### [Radio](https://microbit-micropython.readthedocs.io/en/latest/tutorials/radio.html)

`import radio`

`radio.on()`

`radio.send('duck')`

`radio.receive()`



### [Input/Output pins](https://microbit-micropython.readthedocs.io/en/latest/pin.html)

`pin0.is_touched()`

`pin1.read_analog()`

`pin2.write-digital(1)`



### LED Display (text, [image](https://microbit-micropython.readthedocs.io/en/latest/image.html))

`display.scroll('hello world')`

`display.show(Image.DUCK)`



### [Temperature](https://microbit-micropython.readthedocs.io/en/latest/microbit.html?highlight=temp#microbit.temperature)

`temperature()`



### [Neopixels](https://microbit-micropython.readthedocs.io/en/latest/pin.html)

`import neopixel`

`neopixel.Neopixel(pin0, 10)`

`neopixel.Neopixel.show()`

### [Pause](https://microbit-micropython.readthedocs.io/en/latest/microbit.html#microbit.sleep)

`sleep(500)`

 

## Coding concepts

### Variables

`direction = compass.heading()`

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
elif: accelerometer.was_gesture("face down")
    display.show(Image.HAPPY)
else:
     display.clear()
```

### MicroPython Easter Eggs

`import love()`


