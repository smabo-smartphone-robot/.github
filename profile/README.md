# smabo

*English / [日本語](./README_jp.md)*

This organization manages the repositories for **smabo**, a robot that holds your smartphone.

smabo has the following features:
- Every part snaps together like blocks — no tools required to assemble or disassemble
- Use your own smartphone as the robot's sensors and face

Since it can be assembled without any tools, it's a great robot for beginners too!

For more details, see the [smabo introduction site](https://smabo-smartphone-robot.github.io).

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
- [smabo-smartphone-robot.github.io](https://github.com/smabo-smartphone-robot/smabo-smartphone-robot.github.io)
    - Manages the smabo site (overview, setup instructions, design docs, etc.)
