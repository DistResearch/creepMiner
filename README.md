creepMiner
===========

[![Join the chat at https://gitter.im/creepminer/lobby](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/creepminer/lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![Join the chat at https://discord.gg/qnjyVQt](https://img.shields.io/badge/join-discord-blue.svg)](https://discord.gg/qnjyVQt)
[![GPLv3](https://img.shields.io/badge/license-GPLv3-red.svg)](LICENSE.md)

## What is the creepMiner

The creepMiner is a client application for mining Burst on a pool or solo. For more informations about Burst follow [this link](https://www.burst-team.us/).
It is written in C++ and therefore can be compiled on different operating systems.
It is designed multi-threaded to reach the best performance.

## Features

- Mine with your **CPU** (__SSE2__/__SSE4__/__AVX__/__AVX2__) or your **GPU** (__OpenCL__, __CUDA__)
- Mine **solo** or in a **pool**
- Filter bad deadlines with the auto target deadline feature
- Build a network of several miners with the forwarding feature
- Watch the status of the miner in your web browser on every device

## Build Status

| Platform | Master | Development |
| -------- | ------ | ----------- |
|   Linux   | [![Build Status](https://travis-ci.org/Creepsky/creepMiner.svg?branch=master)](https://travis-ci.org/Creepsky/creepMiner) | [![Build Status](https://travis-ci.org/Creepsky/creepMiner.svg?branch=development)](https://travis-ci.org/Creepsky/creepMiner) |
|   Windows   | [![Build status](https://ci.appveyor.com/api/projects/status/8c4pu0t70riqydny/branch/master?svg=true)](https://ci.appveyor.com/project/Creepsky75522/creepminer/branch/master) | [![Build status](https://ci.appveyor.com/api/projects/status/8c4pu0t70riqydny/branch/master?svg=true)](https://ci.appveyor.com/project/Creepsky75522/creepminer/branch/development) |

## Quickstart

For Windows and Debian: download and install the [latest release](https://github.com/Creepsky/creepMiner/releases/latest)

The install dir for Linux is `/opt/creepMiner-{version}`.

The home dir for Linux is `~/.creepMiner/{version}`, for Windows `C:\Users\You\.creepMiner\{version}`.

For all others:
1. Install [Python](https://www.python.org/)
2. Install [Conan](https://conan.io/downloads): `pip install conan`
3. Install [Poco](https://pocoproject.org/download/index.html): `conan install . -s compiler.libcxx=libstdc++11 --build=missing` (inside the creepMiner root dir)
4. Create the project by executing one of the following commands
- **CPU** (SSE2, SSE4, AVX, AVX2) + **GPU** (OPENCL, CUDA) version: 
```
cmake CMakeLists.txt
```
- **CPU only** (SSE2, SSE4, AVX, AVX2) version:
```
cmake CMakeLists.txt -DNO_GPU=ON
```
- **CPU only minimal** (SSE2) version (for example for single-board computers):
```
cmake CMakeLists.txt -DMINIMAL_BUILD=ON
```
5. Make the project `make` (or `make -j <number of cores to use>` for a faster way)
6. Change your configuration file (located at `~/.creepMiner/<version>/config.json`)

### Run

1. Follow the [Setting up the miner](https://github.com/Creepsky/creepMiner/wiki/Setting-up-the-miner) documentation.
2. Start the mining with `./run.sh` or in a detached `screen` by `./screen.sh`.
3. To enter the screen attach by `screen -r creep`.
4. To detach the screen use the keyboard shortcut `CTRL + A + D`.

## Instructions

- [**FAQ**](https://github.com/Creepsky/creepMiner/wiki/FAQ)
- Compilation & Installation
    - [**Conan** (recommended for all operating systems)](https://github.com/Creepsky/creepMiner/wiki/Compilation-&-Installation-with-Conan)
    - [Windows](https://github.com/Creepsky/creepMiner/wiki/Compilation-&-Installation-on-Windows)
    - [Linux](https://github.com/Creepsky/creepMiner/wiki/Compilation-&-Installation-on-Linux)
    - [MacOS](https://github.com/Creepsky/creepMiner/wiki/Compilation-&-Installation-on-macOS)
- [Setting up the miner](https://github.com/Creepsky/creepMiner/wiki/Setting-up-the-miner)
- [Forwarding](https://github.com/Creepsky/creepMiner/wiki/Forwarding)
- [Solo mining](https://github.com/Creepsky/creepMiner/wiki/Solo-mining)
- [The mining process and optimizations](https://github.com/Creepsky/creepMiner/wiki/The-mining-process-and-optimizations)

## Dependencies

- [POCO C++ libraries](https://pocoproject.org) ([Boost Software License 1.0](https://pocoproject.org/license.html))
- [OpenSSL](https://www.openssl.org) ([Apache style license](https://www.openssl.org/source/license.html))
