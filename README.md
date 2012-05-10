MonkeySee
======

## What is it?
A simple utilitary for visually recording logs which would get played (interpreted) by a robo-car controlled by an `ATmega16` microcontorller.
This is an academic project. It's written in JavaScript on HTML5's canvas.

## The whole
This project is the recorder part of a record-play system. It is the MonkeySee part of the MonkeySee - MonkeyDo project developed as an assignment project in the "Design with microprocessors" class at Polytechnic University of Bucharest.

## Demo
[iuliux.ro/monkeysee/](http://iuliux.ro/monkeysee/)

## Output language:
MonkeySee outputs in a format that has to be interpreted by the AVR-C program running on the car-robot's microcontroller.
An example of the format:

    (^) 1126
    (v) 321
    Comment on this line
    (>v) 1483
        (^) 214
    (<^) 860
    Comment here too (<-) 33
    (-) 1522

### Symbols' meaning:
* `<` - left
* `>` - right
* `^` - forward
* `v` or `V` - backward
* `-` - brake
* `#` - include other `.doit` file (TODO)

Action symbols are put in brackets.

### A command has two parts:
* _action_ _part_ (e.g. `(>v)`) - if two symbols are present, the first one always represents the steering
* _duration_ _part_ - the amount of time the command is active measured in *milliseconds*

### Commands format as a regex:

    .*\([><]?[^Vv-#]\)[ \t]*[0-9]+\\n

Everything before the `(` is ignored, but after the `)`, only whitespace followed by a number and end-of-line can follow.

## Using OpenSource tools:
* [GameJs](http://gamejs.org/)
* [box2dweb](http://code.google.com/p/box2dweb/)
* [Downloadify](https://github.com/dcneiner/Downloadify)
