# smabo

*English / [日本語](./README_jp.md)*

This organization manages the repositories for **smabo**, a robot that holds your smartphone.

smabo has the following features:
- Every part snaps together like blocks — no tools required to assemble or disassemble
- Use your own smartphone as the robot's sensors and face

Since it can be assembled without any tools, it's a great robot for beginners too!

For more details, see the [smabo introduction site](https://smabo-smartphone-robot.github.io).


# What smabo can do

| Feature | What it does | What you need |
|---|---|---|
| [Face and expressions](https://smabo-smartphone-robot.github.io/en/guides/smabo_face/) | The phone's screen becomes smabo's face; change its expression and gaze | smabo-app |
| [Audio processing](https://smabo-smartphone-robot.github.io/en/guides/audioproc/) | Talk to it after a wake word (speech recognition); make it say anything | smabo-app + smabo-brain |
| [Image processing](https://smabo-smartphone-robot.github.io/en/guides/imgproc/) | Recognizes AR markers, colors, faces and QR codes with the camera, and follows them with its eyes, neck or wheels | smabo-app + smabo-brain |
| Manual control | Drive with a joystick and move the servos from the browser | smabo-web + smabo-esp32 |
| [Navigation](https://smabo-smartphone-robot.github.io/en/guides/nav/) | Builds a map with its LiDAR (SLAM) and drives itself to a goal | smabo-brain-ros |
| [Motion planning](https://smabo-smartphone-robot.github.io/en/guides/plan/) | Plans and runs arm motions with MoveIt 2 | smabo-brain-ros |

No robot yet? Try smabo-brain(-ros) and smabo-web with [smabo-sim](https://github.com/smabo-smartphone-robot/smabo-sim).

# How it fits together

```
 smabo-app (phone)        smabo-web (browser)
 face, sensors, voice     control, visualization
        |                          |
        +-------- WebSocket -------+
                     |
     smabo-brain (or smabo-brain-ros)
     relay, odometry, image / speech
     processing, Nav2, MoveIt 2
                     |
                 WebSocket
                     |
     smabo-esp32 (or smabo-sim)
     motors, servos, encoders, LiDAR
```

Every device connects to smabo-brain (or smabo-brain-ros), which relays the messages between them.

# Repositories

The repositories related to smabo are as follows:
- [smabo-app](https://github.com/smabo-smartphone-robot/smabo-app)
    - The smartphone app
    - Uses the phone as the robot's sensors and face
- [smabo-esp32](https://github.com/smabo-smartphone-robot/smabo-esp32)
    - Firmware for the ESP32 microcontroller
    - Controls the robot's actuators (motors, etc.)
- [smabo-brain](https://github.com/smabo-smartphone-robot/smabo-brain)
    - The hub that relays communication between smabo's components
    - Handles advanced processing such as image processing and AI
- [smabo-brain-ros](https://github.com/smabo-smartphone-robot/smabo-brain-ros)
    - Wraps smabo-brain's communication layer from WebSocket to ROS 2 communication (DDS)
    - Makes ROS's extensive libraries and tools (nav2, MoveIt, etc.) available to smabo (optional, not required)
- [smabo-web](https://github.com/smabo-smartphone-robot/smabo-web)
    - A browser-based auxiliary tool for changing smabo's settings, manual control, and visualizing sensor data
- [smabo-hardware](https://github.com/smabo-smartphone-robot/smabo-hardware)
    - Contains smabo's assembly instructions
    - Manages the STL and STEP files for each part
- [smabo-sim](https://github.com/smabo-smartphone-robot/smabo-sim)
    - A simulator that stands in for smabo-esp32 (MuJoCo)
    - Try smabo-brain(-ros) and smabo-web as they are, without the real robot
- [smabo-protocol](https://github.com/smabo-smartphone-robot/smabo-protocol)
    - The single source of the protocol between the repositories (topics and types)
    - Generates the definition files each repository uses
- [smabo-smartphone-robot.github.io](https://github.com/smabo-smartphone-robot/smabo-smartphone-robot.github.io)
    - Manages the smabo site (overview, setup instructions, design docs, etc.)

# Getting started

1. Build smabo from 3D-printed parts with the assembly guides on the [smabo introduction site](https://smabo-smartphone-robot.github.io/en/) (part files in [smabo-hardware](https://github.com/smabo-smartphone-robot/smabo-hardware))
2. Start and connect smabo-brain, smabo-web, smabo-app and smabo-esp32 by following the [startup guide](https://smabo-smartphone-robot.github.io/en/guides/startup/)

# Contributing

Bug reports, ideas and pull requests are welcome. Open an issue in the repository concerned and follow its template.
See [CONTRIBUTING.md](https://github.com/smabo-smartphone-robot/.github/blob/main/CONTRIBUTING.md) for how to work across the repositories.

# License

All repositories are under the [MIT License](https://opensource.org/license/mit).
