# OpenOB
[![PyPI version](https://badge.fury.io/py/OpenOB.png)](http://badge.fury.io/py/OpenOB) [![Build Status](https://travis-ci.com/JamesHarrison/openob.svg?branch=master)](https://travis-ci.com/JamesHarrison/openob)

*There is a mailing list available for [OpenOB users](http://lists.talkunafraid.co.uk/listinfo/openob-users) to share experiences and discuss future development.*

OpenOB (Open Outside Broadcast) is a simple Python/GStreamer based application which implements a highly configurable RTP-based audio link system.

It is primarily designed for broadcast applications including (but not limited to) contribution links, emission links, talkback, and intranet audio distribution systems.

## NOTICE

**The openob project is not being actively maintained or developed. Use at your own risk.**

Due to time constraints and focus elsewhere I'm simply not able to do the major refactoring required to update OpenOB for modern GStreamer/Python, let alone the tidying up and improvements that it could really use under the hood.

It's open source - if you'd like to take it on, fork away!

# Install

Here is the OpenOB and GStreamer installation guide on Debian 12.2 using Python 3

** Install dependencies

```bash
sudo apt-get install libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev libgstreamer-plugins-bad1.0-dev gstreamer1.0-plugins-base gstreamer1.0-plugins-good gstreamer1.0-plugins-bad gstreamer1.0-plugins-ugly gstreamer1.0-libav gstreamer1.0-tools gstreamer1.0-x gstreamer1.0-alsa gstreamer1.0-gl gstreamer1.0-gtk3 gstreamer1.0-qt5 gstreamer1.0-pulseaudio python3-gst-1.0 gir1.2-glib-2.0 gir1.2-gtk-3.0 python3-setuptools redis-server -y

** Modify the redis-server settings

```sudo nano /etc/redis/redis.conf```

**In networks find <bind 127.0.0.1 -::1> and replace it with <bind 0.0.0.0>**
**Restart redis-server: ```sudo service redis-server restart```**

## Firewall config

If you're using a firewall you should allow TCP ports 6397 and UDP ports 3000

## Clone and Installing OpenOB

Clone the repository into a folder
```git clone https://github.com/jamesharrison/openob.git && cd openob```

Build the source code
```python3 setup.py build```

Install the package on the system
```sudo python3 setup.py install```

**Done!**

## Licensing and Credits

OpenOB was developed by James Harrison, with chunks of example code used from Alexandre Bourget and various other GStreamer documentation sites such as the PyGST manual.

Copyright (c) 2018, James Harrison

License is 3-clause BSD:

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following  conditions are met:

* Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.
* Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.
* Neither the name of the OpenOB project nor the names of its contributors may be used to endorse or promote products derived from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL JAMES HARRISON OR OTHER OPENOB CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
