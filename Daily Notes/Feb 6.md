# February 6, 2024

## Abstraction Layers:
In order of most abstract to least abstract...
* Actual applications/Programs
* Libraries: Abstract away some particular task (e.g. controlling a Spark MAX motor controller)
  * (e.g. generative AI example)
  * LLM
  * Machine learning
  * Generator
  * Image
* OS: Manage hardware access
* Hardware: CPU/Memory/...

## chatGPT:
* Has access to pretty much everything on the internet and can find out patterns in it
* Get input of some text
* Predicts the next word using statistics (e.g. token = blue, next word e.g. "sky")
* This can be adapted to images as well
  * Get input of some text + some image (or blank image)
  * Predict next pixel
  * Feed this back into the generator and repeat until image exists
  * 90% sure image generators have some sort of supervisor that also judges whether the image they create is good enough

## Scale:
* Lots of students don't understand scale, so here's an example:
* 1 human = ~1 calculation / second
* Chip with 5 GHz = 5 billion calculations / second (assuming each cycle actually does an operation)
* e.g. Earth takes 50 million steps to walk around Earth.
* If a human takes 1 step/second, and a computer takes 5 billion steps/second...
  * You take 1 step... the computer walks around Earth 100 times.

## Solving problems with computers:
* Have a problem.
  * Programmers write a program ("code") to solve problems
  * Code = instructions for the computer
  * Hardware runs instructions
* Have hardware.