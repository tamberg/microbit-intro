# Introduction to the micro:bit

## Get started
- Open https://makecode.microbit.org/
- Connect the micro:bit via USB
- LED on micro:bit turns orange
- Save the .hex file to "USB Drive"
- LED on micro:bit will blink yellow until the file has been transferred. 

<img src="images/ide.png" width="512" />
<img src="images/micro-bit-front-back.png" width="512" />

## Show LEDs ♥
<img src="images/leds.png" width="512" />

## Show icon
<img src="images/microbit-heart.png" width="512" title="(c) Microbit.org" />

```
basic.showIcon(IconNames.Heart)
```

## Hello, World
<img src="images/hello.png" width="296" />

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
on button A pressed
	showstring A
on button B pressed
	showstring B
	
<img src="images/blocksAB.png" width="512" />

<img src="images/stringAB.png" width="296" />

## Counter (variable)
<img src="images/variable.png" width="512" />

<img src="images/counter.png" width="296" />

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
<img src="images/dice.png" width="512" />

```
input.onGesture(Gesture.Shake, function () {
    basic.showNumber(Math.randomRange(1, 6))
})
```

Or with a variable

<img src="images/dice-with-variable.png" width="512" />


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

=> make two, see who wins

## Beep
sound
	how to connect the hardware
	on shake
		set pin

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
- See https://makecode.microbit.org/projects
