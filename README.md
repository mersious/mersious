### Mersad Masoud

**Embedded and robotics engineer.** I build the runtime layer that keeps autonomous systems alive, observable and reproducible.

Currently in the SoC department at SoftwareMotion, on the platform software of an **L4 autonomous driving stack**, in C++ on ROS 2 and Linux. Building robots since 2018, teaching people to build them for almost as long.

---

#### At work

*Closed source, so descriptions rather than links.*

- **Execution Manager.** A ROS 2 component lifecycle manager, structured as a MAPE-K feedback loop.
  - Monitor grew from passive health checks into active channel monitoring
  - Later split into separate health, diagnostic and guardian nodes
- **Alarm mechanism.** A persistent fault registry keyed by node and error code.
  - Fault lifecycle derived from first-seen and last-seen timestamps
  - Three recovery models: terminal, transient, channel
- **Recording and replay.** ROS 2 bag recording, so a recorded drive can be re-simulated exactly.
  - Subprocess lifecycle via fork and execl, atomic recording flag, clean SIGINT shutdown
  - Timestamped config and calibration snapshots captured alongside every bag
- **Test automation tool.** A production Qt5 desktop application for remote ROS 2 package testing.
  - Deploys a package to a target over SSH, runs it, pulls the artifacts back
  - Reviewing my own code found a race on a cross-thread queue and a dangling pointer in a Qt log handler
- **ELF/DWARF extractor.** A C++ port of a Python DWARF parser for an ECU toolchain.
  - Pulls signal metadata out of ECU binaries to generate A2L calibration files
  - DWARF is a graph of type relationships, not a flat list, so extraction means walking that graph

#### Recent side project

**[Mashinak](https://github.com/mersious/Mashinak)** · **[live](https://mersious.github.io/Mashinak/)**

An interactive map of what a car actually does for its driver, from SAE Level 0 to Level 5.

- Pick a level, pick a feature, see what it senses, where the decision is made, what it moves, and what it depends on
- Every feature is drawn as `senses -> decided in -> acts through`: AEB does not brake, it asks the ESC unit to brake
- The Global view is pure engineering, while EU, US and CN overlay the regulatory regime per level with rule numbers
- State lives in the URL, so `#eu/L3/ALKS` is a link you can send someone
- Content is typed data with ids as string-literal unions, so a typo in a dependency fails the build instead of quietly breaking the graph

> It exists because engineers join automotive projects every day without ever having been told what ESC actually is.

#### Before that

- **ZLab, FANAP Advanced Technologies Lab.** Embedded Systems Lead.
  - Connected-vehicle fleet platform: ESP32, IMU and GNSS fusion, MQTT telemetry, collision prediction
  - Connected-worker safety system fielded in an underground mine in Zanjan: UWB positioning at 30 cm, LoRaWAN telemetry, vital-sign monitoring, v1 to feedback to v2 on site
  - Two humanoid robots, Alfred and Kiyan
  - Self-checkout smart cart, pivoted from object detection to barcode and weight-sensor fusion once detection broke down at real catalog scale
- **Mositto Innovation Center.** Instructor, then competition coach, then head of the academy.
  - 150+ students mentored
  - Took two teams to **third place at RoboCup Asia-Pacific 2021** in Aichi, Japan, Primary and Secondary divisions

#### Kit

```text
languages   C++ · Embedded C · Python · Bash
runtime     ROS 2 · DDS · FreeRTOS · Qt5 · Docker
patterns    MAPE-K · component lifecycle · SOLID · real-time
comms       MQTT · REST · LoRaWAN · UWB · CAN · BLE
bench       Linux · CMake · colcon · GDB · gtest · Foxglove
ci          GitLab CI · Jenkins · GitHub Actions
silicon     Horizon J6 E/M · MDC610 · ARM · Jetson · ESP32
```

#### Elsewhere

[**mersious.github.io**](https://mersious.github.io) ·
[LinkedIn](https://www.linkedin.com/in/mersad-masoud) ·
<mersadmasoud@gmail.com>

> **Life · Robots · Liberty**, a free Persian-language robotics series on YouTube, made because no proper free resource existed in Persian for learning the basics.
