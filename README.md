# Introduction to the micro:bit

## Get started
- Open https://makecode.microbit.org/
- Connect the micro:bit via USB
- Save file to "USB Drive"

<img src="images/ide.png" width="512" />

## Show LEDs ♥
<img src="images/leds.png" width="512" />

<img src="images/microbit-heart.png" width="512" title="(c) Microbit.org" />

## Show icon
<img src="images/icon.png" width="512" />

```
basic.showIcon(IconNames.Heart)
```

## Hello, World
<img src="images/hello.png" width="512" />

```
basic.showString("Hello, World!")
```

## Forever
<img src="images/forever.png" width="512" />

```
basic.forever(function () {
    basic.showIcon(IconNames.Heart)
    basic.showIcon(IconNames.SmallHeart)
})
```

## Shake
<img src="images/shake.png" width="512" />

```
input.onGesture(Gesture.Shake, function () {
    basic.showIcon(IconNames.No)
})
basic.showIcon(IconNames.Heart)
```

## Buttons
<img src="images/button.png" width="512" />

```
input.onButtonPressed(Button.A, function () {
    basic.showString("A")
})
input.onButtonPressed(Button.B, function () {
    basic.showString("B")
})
```

## Counter (variable)
<img src="images/variable.png" width="512" />

<img src="images/counter.png" width="512" />

```
let i = 0 // Variable
input.onButtonPressed(Button.A, function () {
    i = 0 // Reset variable
})
input.onButtonPressed(Button.B, function () {
    i += 1 // Increment variable
})
basic.forever(function () {
    basic.showNumber(i)
})
```

## Dice (random number)
<img src="images/random.png" width="512" />

```
input.onGesture(Gesture.Shake, function () {
    basic.showNumber(Math.randomRange(1, 6))
})
```

Or with a variable

<img src="images/random-variable.png" width="512" />


```
let result = 0
input.onGesture(Gesture.Shake, function () {
    result = Math.randomRange(1, 6)
    basic.showNumber(result)
})
```

## Rock, Paper, Scissors
<img src="images/rock-paper-scissors.png" width="512" />

```
let result = 0
input.onGesture(Gesture.Shake, function () {
    result = Math.randomRange(0, 2)
    if (result == 0) {
        basic.showIcon(IconNames.SmallSquare) // Rock
    } else if (result == 1) {
        basic.showIcon(IconNames.Square) // Paper
    } else { // result == 2
        basic.showIcon(IconNames.Scissors)
    }
})
```

Make two, see who wins.

## Beep
Connect an external beeper to Pin *0* and *GND*.

<img src="images/external-beep.png" width="512" />

```
basic.forever(function () {
    pins.digitalWritePin(DigitalPin.P0, 1)
    basic.pause(500)
    pins.digitalWritePin(DigitalPin.P0, 0)
    basic.pause(500)
})
```

## External Button (w/ 3V)
Connect an external button to Pin *2* and *3V*.

<img src="images/external-button-3v.png" width="512" />

```
pins.onPulsed(DigitalPin.P2, PulseValue.High, function () {
    basic.showIcon(IconNames.Heart)
})
```

## External Button (w/ GND)
Connect an external button to Pin *2* and *GND*.

<img src="images/external-button-gnd.png" width="512" />

```
pins.onPulsed(DigitalPin.P2, PulseValue.Low, function () {
    basic.showIcon(IconNames.Heart)
})
pins.setPull(DigitalPin.P2, PinPullMode.PullUp)
```

## Radio Alert
radio
	on shake
		send alarm
	on radio
		ring the alarm

## List
list
	?
## More
- https://github.com/tamberg/microbit-ghoust
- https://makecode.microbit.org/projects
