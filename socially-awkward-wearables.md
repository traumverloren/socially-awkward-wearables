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

# I built an autonomous necklace

![left fill autoplay loop](photos/ml-necklace.mov)

^ We are at a tech conf, and I'm to spend the next 30 minutes talking about my necklace

---

# [fit] Loaded with tech

![left fit](photos/necklace-schema.jpg)


| Hardware: | Software: |
| :--- | :--- |
| - Raspberry Pi | - NodeJS |
| - Arduino | - Tensorflow.js|
| - Camera | - C++
| - LEDs
| - Battery

^ How is it responding?

^ Well, as you can see in these lists, I've utilized a lot of different tech to make this work.

^ Camera is taking a picture every couple seconds

^ Camera is attached to rpi

^ RPI is running NodeJS & tensorflowjs and an image recognition model that determines what it sees in the picture

^ After the ML model on the pi determines how many people it sees, it sends this info to an arduino.

^ The arduino is controlling the lights on the necklace.

^ it updates the colors and patterns of leds based on parameters i've set for how it should respond.

---

# Stephanie Nemeth

![fit left](photos/steph.jpg)

web developer, [@MicrosoftToDo](https://www.twitter.com/microsofttodo)

<br>

| Likes: | Dislikes: |
| :--- | :--- |
| - Fashion | - **Attention in public** |
| - LEDs 
| - Tech things

----

### [fit] I'm *fascinated* with making myself 
### [fit] uncomfortable in public

^ It's usually a guarantee that i'm uncomfortable in social settings. i feel awkward and introverted all the time.

---

# [fit] A wearable that forces me 
# [fit] to be *around people* in order to
# [fit] *not* DRAW ATTENTION

^ I wanted to create a necklace that would be reasonably obnoxious and flashy and attention getting when i was off by myself and would only calm down and turn off when i forced myself to be sociable and surround myself with other people.

---

# [fit] I've been exploring socially awkward 
# [fit] wearables since I started building things

^ I've been exploring making myself uncomfortable in public with wearables over he past couple years without really realizing it.

---

![fill original](photos/dress-1.jpg)
![fill original](photos/dress-2.jpg)
![fill original](photos/dress-3.jpg)
![fill original](photos/dress-4.jpg)


### [tiny.cc/fiber-optic-kit](tiny.cc/fiber-optic-kit)

<br>


^ i was going to a festival
^ saw someone's work in a instructables tutorial and copied it exactly.

^ bought a kit with preset light programs

^ sewed to a dress

---

![fill left](photos/bike-ride.jpg)

## [fit] It was weird for me
## [fit] but people liked it

^ I felt awkward, but got lots of compliments.

^ Self-esteem boost.

---

![fill autoplay loop](photos/intro-clip.mov)

### [tiny.cc/haute-codeture](http://tiny.cc/haute-codeture)

<br>

^ in this project i wanted the lights to be able to be changed by other people.

^ Gave talks about this project last year, check out link

^ I built an app to control the lights

^ Anyone on the web could control the lights

^ Lots of coding: React, NodeJS, MQTT, Arduino

^ Lots of soldering

---

![50% autoplay loop right](photos/haute-app.mov)

## [fit] a web app for your outfit is
## [fit] both good and bad

^ i didn't like being Stuck with keeping my phone on me, to have a network connection

^ Realized I was doing it more to please and focus on other people which is OK but less of the direction i was interested in.

^ Wanted to take away the need direct interaction of others, more focused on me and what i was experiencing. 

---

![fit left autoplay loop](photos/IMG_6459.mp4)

### [tiny.cc/speech-to-image](http://tiny.cc/speech-to-image)

^ this is the last project i did.

^ i wanted to make a necklace that would show accompanying images as i was speaking to someone so they would find me interesting and what to engage in conversation with me.

^ I have a raspberry pi with a touchscreen and a microphone.

^ NodeJS server runningthat is sending audio to the google speech recognition api and then sending those keywords to the google search api from and finally is showing an image that correlates to what i'm saying.

^ Responsive to the environment

^ still needed wifi

---

![fit left autoplay loop](photos/IMG_6459.mp4)

# [fit] I accidently made a thing 
# [fit] with *machine learning* 
# [fit] and hadn't realize it.

🤷‍

### (I just thought I was using an API)

^ Ironically I also didn't realize I had worked with ML in this project until I really looked back and thought about this project again.

^ ML is so ubiquitous/pervasive, I used it here  and didn't really understand that I was using it.

^ I was just using an API that I sent data to and got a response.

---

# Making An Autonomous necklace

![left autoplay loop fill](photos/ml-necklace.mov)

^ I've kind of misled you though. Though this progression of my work is a convincing reason for me to build this necklace, 

^ There was really a defining moment when I decided to build it.

---

### I couldn't keep up with a machine learning study group at work

^But the real reason i built this is because I couldn't keep up with a machine learning study group at work.

^ i had just started a new job at a big tech co and felt really insecure with my skills.

^ Everyone else learning fast

^ i was falling behind from the first study group and was beating myself up about it.

^ i wanted to prove myself & validate my learning style

^ All theoretical, no practical/tangible

^ so i found other ways to learn and decided to create a physical use case for ML that was relevant to me and my interests

---

![autoplay loop](photos/coding-train.mp4)

^ i used 2 resources to start exploring ML:
first is coding train

---

![autoplay loop](photos/ml4a.mp4)

^ second is the ML 4 artist courses by gene kogan
^ i was super inspired by all the experiments artists are doing around ml

^ they gave me ideas on how i could integrate ml into a this new wearable project

---

## TensorFlow.js

^ i wanted to do all the machine learning in JS.

^ Library for training & running machine learning models in the browser
(or Node.js)

^ it's mostly geared towards the browser

^ There were 2 things i wasn't sure if they were even possible when i started:

^ 1. running ml models in node instead of browser

^ 2. run ml models in node on a rpi
 so i wanted to tackle those first before i invested time in making a wearable.

---

![left](photos/tiny-yolo-library.gif)

# Tiny-YOLO

## *Y*ou *O*nly *L*ook *O*nce

<br>
 Fast **in-browser** image detection

^ Pre-trained model

---

![right fill](photos/got-it-working.png)

# [fit] Adapt Tiny-YOLO to work on Node.js

- Use `@tensorflow/tfjs-node`
- Store model files locally
- Modify `import`/`export` statements
- Load image file vs. `MediaDevices.getUserMedia()`

^ lots of minor code changes to do to run browser based models in node instead.

^ warning that i'm not going to show a bunch of code during this talk since this code is v specific to my project.

---

# Autonomous Necklace Recipe

1. ~~Get image recognition ML model running on Node.js~~
2. **Run TensorFlow.js on Raspberry Pi!**
<br/>
<br/>
<br/>

---

![fit](photos/tfjs-pr.png)

^ i got really lucky that the tf.js team had just made a change for this, though it wasn't in released build yet (still in a branch they were working on)

---

![fit](photos/tensorflow-github.png)

^ i needed to use a package (yalc) to build it locally on my pi from their commit, but it worked!

---

# FYI: I'm running on Tensorflow.js 0.14.2

It is a bit hacky, but runs reliable & that's beautiful!

<br/>

If it ain't broke, don't fix it?

^ I did this months ago and honestly don't wanna mess it up

^ Latest tf.js release is 1.2.8

^ Also prepping rc 2.0

---

![left fill](photos/camera-working-1.png)

![right fill](photos/camera-working-2.png)

---

# Autonomous Necklace Recipe

1. ~~Get image recognition ML model running on Node.js~~
2. ~~Run TensorFlow.js on Raspberry Pi!~~
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
4. ~~Create a LED necklace~~
5. **Send image data from the Raspberry Pi to the arduino**

---

# [fit] Communication between the 
# [fit] Raspberry Pi and the arduino

---

![fit](photos/rpi-pinouts.png)

^ Useful for low level communication

^ One for sending, one for receiving

^ Send data from Pi to data pin on Arduino

---

![right fit](photos/pi-serial-issue.png)
![left fit](photos/rpi-loopback.jpg)

^ i had a lot of trouble with this!

^ loopback

---

![inline fit](photos/teensy-serial.png)

---

![](photos/serial-instructions.gif)

^ updating pi config files

^ disable some config settings on boot

---

# [fit] but I had bugs that were really bad

---

# [fit] Power issues on necklace


![left fill autoplay loop](photos/teensy-power-issues.mov)

^ Outside my abilities at the time

^ So switched boards instead

^ FIX THIS!!!

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

^ Lights would pause while processing the JSON received bc arduino is single threaded and very limited resources

^ Oops, that didn't work so well

---

![fit](photos/switched-to-bytes.png)


^ this is code in the NodeJS App
^ what info does the arduino really need
^ what can it be condensed down to
^ 60 & 62

---

# Autonomous Necklace Recipe

1. ~~Get image recognition ML model running on Node.js~~
2. ~~Run TensorFlow.js on Raspberry Pi!~~
4. ~~Create a LED necklace~~
5. ~~Send image data from the Raspberry Pi to the necklace~~
6. **Program the lights to change based on # of people around**

---

# [fit] Non-javascript stuff
### (Write a bunch of C++ on arduino)

![](photos/working.jpg)

---

![fit](photos/change-program.png)

^ get a message, get peopleCount, update program

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

---

![fit](photos/button-program.png)


^ experiment with ability to flip how the necklace responds

^ so it would be calm with no one around and chaotic with many people around

---

![fit](photos/blubbering.png)

^ it was hard and i got demotivated
^ 8mos vs. 3mos
^ always stuff i could have done differently

---

<!-- ## Thank you

![fit](photos/blubbering.png)

^ lots of bugs along the way
^ always stuff i could have done differently

--- -->
# Thanks!

![fit left](photos/steph.jpg)

[stephanie.lol](https://stephanie.lol)

<!-- frontend  -  react  -  js  -  a11y -->

### ✨ Convo starters ✨
fashion  |  **vivienne westwood**  |  ootds

**bojack**  |  dogs


^ i love to talk about non-tech things, so I thought i'd include some convos starters if you see me around please chat!