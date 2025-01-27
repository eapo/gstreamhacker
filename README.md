# GStreamHacker
Audio-Video Processing System for Raspberry Pi and PC based on [GStreamer](https://gstreamer.freedesktop.org/)

## Overview

This project aims to create an efficient audio-video processing system that can recognize specific patterns in real-time, allowing users to trigger commands such as mute, next, dim screen, or play files. The system is designed to run on Raspberry Pi 4 and older laptops/PCs, providing a versatile solution for multimedia applications.

## Features

- **Real-Time Processing**: Utilize GStreamer for low-latency audio and video processing.
- **Pattern Recognition**: Implement custom algorithms to recognize specific audio and video patterns.
- **HDMI Input/Output**: Capture and output HDMI signals using compatible hardware.
- **Cross-Platform**: Compatible with Raspberry Pi OS and various Linux distributions for PCs.
- **User-Friendly Interface**: A simple GUI for configuring settings and monitoring streams.

## Requirements

### Hardware

- **Raspberry Pi 4** (recommended) or older Intel-based laptops/PCs
- HDMI capture card (if needed)
- USB microphone (for optional audio input)
- Reliable power supply (5V/3A for Raspberry Pi)
- High-speed microSD card (Class 10 or UHS) or USB storage for PCs

### Software

- [Raspberry Pi OS](https://www.raspberrypi.org/software/) or any compatible Linux distribution
- [GStreamer](https://gstreamer.freedesktop.org/)
- Additional libraries and dependencies as specified in the installation section

## Installation

### For Raspberry Pi

1. **Download Raspberry Pi OS**: Get the latest version from the [official website](https://www.raspberrypi.org/software/).
2. **Flash the OS onto an SD Card**:
   - Use tools like [balenaEtcher](https://www.balena.io/etcher/) to flash the downloaded image onto your microSD card.
3. **Boot up the Raspberry Pi**:
   - Insert the SD card into your Raspberry Pi and power it on.
4. **Install GStreamer**:
   ```
   sudo apt update
   sudo apt install gstreamer1.0-tools gstreamer1.0-plugins-base gstreamer1.0-plugins-good
   ```
5. **Clone this repository**:
   ```
   git clone https://github.com/eapo/gstreamhacker.git
   cd gstreamhacker
   ```

### For PC/Laptop

1. **Download a Linux Distribution**: Choose a lightweight distribution like Ubuntu or Debian.
2. **Create a Bootable USB Drive**:
   - Use tools like [Rufus](https://rufus.ie/) or [balenaEtcher](https://www.balena.io/etcher/) to create a bootable USB drive.
3. **Boot from USB**:
   - Insert the USB drive into your laptop/PC and boot from it.
4. **Install GStreamer**:
   ```
   sudo apt update
   sudo apt install gstreamer1.0-tools gstreamer1.0-plugins-base gstreamer1.0-plugins-good
   ```
5. **Clone this repository**:
   ```
   git clone https://github.com/eapo/gstreamhacker.git
   cd gstreamhacker
   ```

## Usage

After installation, you can run the main application using:

```
python main.py
```

Follow the on-screen instructions to configure your audio-video input/output settings.

## Contributing

We welcome contributions from developers of all skill levels! If you're interested in helping out, please follow these steps:

1. Fork this repository.
2. Create a new branch.
3. Make your changes and commit them.
4. Push to the branch.
5. Open a Pull Request.

---

## Custom subprojects

We also added a meson option, `custom_subprojects`, that allows the user
to provide a comma-separated list of meson subprojects that should be built
alongside the default ones.

To use it:

```sh
# Clone into the subprojects directory
$ git -C subprojects clone my_subproject
# Wipe dependency detection state, in case you have an existing build dir
$ meson setup --wipe builddir -Dcustom_subprojects=my_subproject
$ meson compile -C builddir
```
