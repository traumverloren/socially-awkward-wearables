autoscale: true
footer: @stephaniecodes

# [fit] How not to read a room:

## [fit] Creating a socially awkward wearable

## <br />
## <br />

### Stephanie Nemeth

#### @stephaniecodes  ✨  stephanie.lol

[.hide-footer]

---

# An Autonomous necklace

![left fill autoplay loop](photos/ml-necklace.mov)

---

# [fit] Look at all this tech!

![left fit](photos/necklace-schema.jpg)


| Hardware | Software |
| :--- | :--- |
| Camera | NodeJS |
| Raspberry Pi | TensorflowJS|
| Arduino | C++
| LEDs
| Battery


---

## [fit] *WHY* is just as important as *HOW*

---

# Stephanie Nemeth

![fit left](photos/steph.jpg)

web developer, [@MicrosoftToDo](https://www.twitter.com/microsofttodo)

frontend  -  react  -  js  -  a11y

### ✨ Convo starters ✨
fashion  |  **vivienne westwood**  |  ootds

**bojack**  |  the heartshe, she holler

**dogs** | career changing

---

### [fit] I'm *fascinated* with making myself 
### [fit] uncomfortable in public

^ I'm a bit introverted, awkward & anxious in social situations.
^ I'm usually always uncomfortable in social settings.

---

# [fit] A wearable that forces me 
# [fit] to be *around people* in order to
# [fit] *not* DRAW ATTENTION

^It's terrifying & counterinituitive but

---

# [fit] Earlier experiments with wearables

^ Over past couple years, I've made a couple of wearable projects to gradually explore wearing lighted wearables in public

^ How people react in general

^ How I react to people reacting

---

![fill](photos/dress-1.jpg)
![fill](photos/dress-2.jpg)
![fill](photos/dress-3.jpg)
![fill](photos/dress-4.jpg)

^ fiber optic whip kit

^ base is a flashlight with programmed programs

^ stitched to white dress sewn by my mom.

---

![fill left](photos/wip-1.jpg)

# Fiber Optic Dress

- Bought a kit: [tiny.cc/fiber-optic-kit](tiny.cc/fiber-optic-kit)
- Followed an Instructables tutorial
- No coding, pre-programmed
- No soldering, only sewing

---

![fill left](photos/bike-ride.jpg)

## [fit] First time wearing lights 
## [fit] & people liked it!

---

![fill left](photos/bike-ride.jpg)

## [fit] A Bit Lifeless

^ ~6 months coding experience
^ Next logical step was to actually code something

---

![fill autoplay loop](photos/intro-clip.mov)


^ Multiple coordinated pieces
^ Anyone on the web could control the lights

---

![50% autoplay loop right](photos/haute-app.mov)

# Haute Codeture

- Lots of coding:
    - React, NodeJS, MQTT, Arduino
- Lots of soldering
- [tiny.cc/haute-codeture](http://tiny.cc/haute-codeture)

---

![fill left](photos/haute-codeture-2.jpg)

## People *really* liked controlling how I looked.

---

![fill left](photos/haute-codeture-2.jpg)

## *Limitations:*
## Dependent on wifi and an app

^ Stuck with keeping my phone on me, having a network connection

---

# Speech-to-Image Necklace

![fit left autoplay loop](photos/IMG_6459.mp4)

- Some coding:
    - NodeJS
    - Google cloud speech recognition API
    - Google Custom Search API
- No soldering
- [tiny.cc/speech-to-image](http://tiny.cc/speech-to-image)

---

![fit left autoplay loop](photos/IMG_6459.mp4)

# [fit] Responsive to the environment

# [fit] but needs wifi to work

---

# [fit] I accidently made something
# [fit] with *machine learning* & didn't realize it.

🤷‍

## (I just thought I was using an API)

---

# Making An Autonomous necklace

![left autoplay loop fill](photos/ml-necklace.mov)

^ rest of the talk I want to talk through how i built this and the different tech challenges i faced

---

### I couldn't keep up with a machine learning study group at work.

^But the real reason i built this is because I couldn't keep up with a machine learning study group at work that was doing a big MOOC course.

^ Everyone else learning fast
^ All theoretical no practical/tangible

^ Prove myself & Validate my learning style

---

![autoplay loop](photos/coding-train.mp4)

^ NOTES

---

![autoplay loop](photos/ml4a.mp4)

^ NOTES

---


## It was hard and
## I got demotivated

^ Build time: 8 months vs. 3 months

---

## I still know very little 
## about machine learning

---

## [fit] I'm good at figuring out things
## I don't understand

^ demotivated alot of this year
^ easy to hyperfocus and tweak one bit

---

<!-- [.build-lists: true]

# Autonomous Necklace Recipe

1. Get image recognition ML model running on **Node.js**
2. Run TensorFlow.js on **Raspberry Pi!**
3. Send camera pic to image recognition model on Raspberry Pi
4. Create a LED necklace
5. Send image data from the Raspberry Pi to the necklace
6. Make the necklace responsive to data

--- -->

# Autonomous Necklace Recipe

1. **Get image recognition ML model running on Node.js**
<br/>
<br/>
<br/>
<br/>
<br/>

---

## TensorFlow.js

^ Library for training & running machine learning models in the browser
(or Node.js)


^ it's mostly geared towards the browser

---

![left](photos/tiny-yolo-library.gif)

# Tiny-YOLO

## *Y*ou *O*nly *L*ook *O*nce

- Pretrained model
- Fast **in-browser** image detection

---

![right fill](photos/got-it-working.png)

# [fit] Adapt Tiny-YOLO to work on Node.js

- Use `@tensorflow/tfjs-node`
- Store model files locally
- Modify `import`/`export` statements
- Load image file vs. `MediaDevices.getUserMedia()`

---

# Autonomous Necklace Recipe

1. ~~Get image recognition ML model running on Node.js~~
2. **Run TensorFlow.js on Raspberry Pi!**
<br/>
<br/>
<br/>
<br/>

---

![fit](photos/tfjs-pr.png)

---

![fit](photos/tensorflow-github.png)

---

# FYI: I'm running on Tensorflow.js 0.14.2

It is a bit hacky, but runs reliable & that's beautiful!

<br/>

If it ain't broke, don't fix it?

^ I did this months ago and honestly don't wanna mess it up

^ Latest tf.js release is 1.2.8

^ Also prepping rc 2.0

---

# Autonomous Necklace Recipe

1. ~~Get image recognition ML model running on Node.js~~
2. ~~Run TensorFlow.js on Raspberry Pi!~~
3. **Send camera pic to image recognition model on Raspberry Pi**
<br/>
<br/>
<br/>

---

# [fit] Send camera pic to image recognition model on Raspberry Pi

- Hookup PiCamera 
- Use `node-canvas` & create a canvas for the pic
- Crop image to match what model expecting (416 x 416)
- Turn into a tensor & send to the model!

---

![left fill](photos/camera-working-1.png)

![right fill](photos/camera-working-2.png)

---

# Autonomous Necklace Recipe

1. ~~Get image recognition ML model running on Node.js~~
2. ~~Run TensorFlow.js on Raspberry Pi!~~
3. ~~Send camera pic to image recognition model on Raspberry Pi~~
4. **Create a LED necklace**
<br/>
<br/>

---

# [fit] Reuse hardware and materials I already had

![left](photos/blinky-kit.jpg)
![right fill](photos/blinkytiles-stock.jpg)

---

![left fill](photos/blinkytiles-top.jpg)
![right autoplay loop fit](photos/blinkytiles-wearable.MOV)

---

 Use the blinkytiles but control them with an arduino

![inline 80%](photos/blinkytiles-github.png)

[https://github.com/jasoncoon/BlinkyTileFastLED](https://github.com/jasoncoon/BlinkyTileFastLED)

---

![fit autoplay loop](photos/blinkytiles-arduino-test.mov)
![fit](photos/blinkytiles-tweet-2.png)

---

![30%](photos/necklace-1.jpg)
![](photos/necklace-3.jpg)

---

# Autonomous Necklace Recipe

1. ~~Get image recognition ML model running on Node.js~~
2. ~~Run TensorFlow.js on Raspberry Pi!~~
3. ~~Send camera pic to image recognition model on Raspberry Pi~~
4. ~~Create a LED necklace~~
5. **Send image data from the Raspberry Pi to the necklace**

---

# [fit] Physically connect the 
# [fit] Raspberry Pi to the necklace

---

![fit](photos/rpi-pinouts.png)

^ Useful for low level communication
^ One for sending, one for receiving
^ Send data from Pi to data pin on Arduino

---

![right fit](photos/pi-serial-issue.png)
![left fit](photos/rpi-loopback.jpg)

---

![inline fit](photos/teensy-serial.png)

---

![](photos/serial-instructions.gif)

^ updating pi config files
^ disable some config settings on boot

---

# [fit] 🐛 Bugs :( 🐜

---

# [fit] Power issues on necklace


![left fill autoplay loop](photos/teensy-power-issues.mov)

^ long wires
^ 5V possible, but with a bit of modification
^ Outside my abilities at the time
^ So switched boards instead

---

![](photos/teensy.jpg)
![](photos/metro-mini.jpg)

^ Teensy 3.3V, 5V tolerant
^ Metro Mini 5V output
^ Blinkytiles need 5V
^ I had one lying around

---

# [fit] Raspberry Pi Crashing

![left fit](photos/memleaks.jpg)

^ monitor with htop

---
[.build-lists: true]

# Remember this project?

![right fit autoplay loop](photos/IMG_6459.mp4)

---

# [fit] it was still running at startup 
# [fit] & HAD A MEMORY LEAK 
#<br>
# 🤦‍

![right fit autoplay loop](photos/IMG_6459.mp4)

---

# Autonomous Necklace Recipe

1. ~~Get image recognition ML model running on Node.js~~
2. ~~Run TensorFlow.js on Raspberry Pi!~~
3. ~~Send camera pic to image recognition model on Raspberry Pi~~
4. ~~Create a LED necklace~~
5. **Send image data from the Raspberry Pi to the necklace**

---

# [fit] What format do I use to send data?

![](photos/serial-coding.png)

---


# [fit] ‍I use json everywhere else,
# [fit] I'll use JSON here

![](photos/serial-coding.png)

---

[.build-lists: true]

# JSON on Arduino is a thing!

![left fit](photos/serial-arduino.png)

^ Hey, there's an Arduino JSON library

^ Wow, it worked!

---

# [fit] But this was a bad decision

---

![fit](photos/mem-issues-2.png)

^ Lights would pause while processing the JSON received

^ Oops, that didn't work so well

---

![fit](photos/switched-to-bytes.png)


^ this is code in the NodeJS App
^ what info does the arduino really need
^ what can it be condensed down to
^ 60 & 62

---

![](photos/arduino-commits.png)

^ actually started writing the C++ for the light programs at end of June

---

![fit](photos/workonwearables.png)

---

# Autonomous Necklace Recipe

1. ~~Get image recognition ML model running on Node.js~~
2. ~~Run TensorFlow.js on Raspberry Pi!~~
3. ~~Send camera pic to image recognition model on Raspberry Pi~~
4. ~~Create a LED necklace~~
5. ~~Send image data from the Raspberry Pi to the necklace~~
6. **Program the lights to change based on # of people around**

---

# [fit] Non-javascript stuff
### (Write a bunch of C++ on arduino)

![](photos/working.jpg)


---

![fit](photos/change-program.png)

---

[tiny.cc/ml-necklace](http://tiny.cc/ml-necklace)


![fit](photos/change-program.png)

---

![fit](photos/test.png)

^ Don't wait to the end to actually wear it

---

![right fit](photos/necklace-schema.jpg)

![left fit](photos/gurtel.jpg)

^ first idea was to stuffy everything in a fanny pack but that was not working.

^ too much stuff, too big

---

# [fit] Sometimes, I've had enough
##<br>
## 😖 😩 😫

![fit](photos/button-program.png)

^ I decided to add one more feature I hadn't planned for
^ a way to turn off the lights completely
^ ability to flip how the necklace responds

---

![fit](photos/button-program.png)

---

![fit](photos/blubbering.png)

^ lots of bugs along the way
^ always stuff i could have done differently

---

## Thank you

![fit](photos/blubbering.png)

^ lots of bugs along the way
^ always stuff i could have done differently