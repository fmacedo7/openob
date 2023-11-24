# OpenOB
[![PyPI version](https://badge.fury.io/py/OpenOB.png)](http://badge.fury.io/py/OpenOB) [![Build Status](https://travis-ci.com/JamesHarrison/openob.svg?branch=master)](https://travis-ci.com/JamesHarrison/openob)

*There is a mailing list available for [OpenOB users](http://lists.talkunafraid.co.uk/listinfo/openob-users) to share experiences and discuss future development.*

OpenOB (Open Outside Broadcast) is a simple Python/GStreamer based application which implements a highly configurable RTP-based audio link system.

It is primarily designed for broadcast applications including (but not limited to) contribution links, emission links, talkback, and intranet audio distribution systems.
__________________________________________________________

## Fork of the OpenOB Project with aptX Codec Support

This repository is a fork of the OpenOB project, a powerful solution for streaming audio over IP based on the AES67 protocol. This fork was created to include support for a new audio codec, aptX.

## Main changes:

### Implementation of the aptX codec
The highlight of this release is the addition of support for the aptX codec. aptX is known for delivering exceptional audio quality, especially in environments with limited bandwidth. Its inclusion expands the options available for high-fidelity audio transmission in OpenOB.

### Compatibility with the Original Project
This fork remains compatible with the original OpenOB project, maintaining all existing functionality for audio transmission over IP with the AES67 protocol. All aptX-specific improvements and modifications have been integrated without compromising the integrity of the main project.

## How to use

1. **Clone the Repository**
```bash
https://github.com/fmacedo7/openob.git
```
2. **Update and install the dependencies***
```bash
sudo apt-get update && sudo apt-get upgrade && sudo apt-get install libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev libgstreamer-plugins-bad1.0-dev gstreamer1.0-plugins-base gstreamer1.0-plugins-good gstreamer1.0-plugins-bad gstreamer1. 0-plugins-ugly gstreamer1.0-libav gstreamer1.0-tools gstreamer1.0-x gstreamer1.0-alsa gstreamer1.0-gl gstreamer1.0-gtk3 gstreamer1.0-qt5 gstreamer1.0-pulseaudio python3-gst-1.0 gir1.2-glib-2.0 gir1.2-gtk-3.0 python3-setuptools redis-server -y
```
3. **Modify the redis-server settings**
You need to allow redis to access external machines by modifying its network settings in redis.conf
```bash
sudo nano /etc/redis/redis.conf
```
Find the section called networks and leave something similar to
>bind 127.0.0.1
>bind 0.0.0.0
Restart redis-server to apply the settings
```bash
sudo service redis-server restart
```
4. **Firewall**
You need to make sure that ***TCP port 6397*** and ***UDP port 3000*** are allowed.

5. **Building and installing OpenOB**
Build the source code
```bash
python3 setup.py build
```
6. **Install the packages on the system**
```bash
sudo python3 setup.py install
```
7. **Check the installation**
```bash
openob --help
```
## Acknowledgments
We are grateful to the OpenOB community for providing a solid foundation and to the original team for developing and maintaining this project. This fork seeks to expand OpenOB's capabilities, bringing innovation through the implementation of the aptX codec.

## Licensing and Credits

OpenOB was developed by James Harrison, with chunks of example code used from Alexandre Bourget and various other GStreamer documentation sites such as the PyGST manual.

Copyright (c) 2018, James Harrison

License is 3-clause BSD:

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following  conditions are met:

* Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.
* Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.
* Neither the name of the OpenOB project nor the names of its contributors may be used to endorse or promote products derived from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL JAMES HARRISON OR OTHER OPENOB CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
