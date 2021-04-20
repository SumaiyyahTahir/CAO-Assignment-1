# CAO Assignment

This repository has the code for Assignment 1, making our own 64 bit OS using the [provided videos](https://www.youtube.com/watch?v=FkrpUaGThTQ).

## Tools

These tools are required to make the OS

```bash
Docker for creating the build environment
Visual Studio Code as text editor
QEMU for emulating the OS
```

## Building Docker Image
```bash
docker build buildenv -t myos-buildenv
```

## Build
To enter build-environment
```bash
Linux or MacOS: docker run --rm -it -v "$pwd":/root/env myos-buildenv
Windows (CMD): docker run --rm -it -v "%cd%":/root/env myos-buildenv
Windows (PowerShell): docker run --rm -it -v "${pwd}:/root/env" myos-buildenv
```
Build for x86 architecture
```bash
make build-x86_64
```
Note: type exit to leave the environment
## Emulate
QEMU can be used to emulate the OS. First, QEMU has to be added as an environment variable. The location of QEMU should be specified in the terminal like here, my QEMU was in C drive in Program Files folder:
```bash
qemu-system-x86_64 -cdrom dist/x86_64/kernel.iso -L "C:\Program Files\qemu"
```
## C code
We need gcc and g++ compiler to run C and C++ code in VS Code. [Here is the link on how to install these](https://www.youtube.com/watch?v=Ubfgi4NoTPk)
## Output
