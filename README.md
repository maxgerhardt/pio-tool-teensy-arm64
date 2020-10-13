# pio-tool-teensy-arm64

Teensy tools for PlatformIO and the ARM64 platform.

This is **not** the repo for 32-bit ARM operating systems. For that, see https://github.com/maxgerhardt/pio-tool-teensy-arm

# Usage

A typical fixed `platformio.ini` with which e.g. a Raspbi Pi 3/4 with a 64-bit OS can compile code for a Teensy 4 looks like this:

```
[env:teensy40]
platform = teensy
framework = arduino
board = teensy40 
platform_packages = 
   toolchain-gccarmnoneeabi@https://bintray.com/platformio/tool-packages/download_file?file_path=5966cc5-toolchain-gccarmnoneeabi-linux_aarch64-1.90301.200702.tar.gz
   tool-teensy@https://github.com/maxgerhardt/pio-tool-teensy-arm64/archive/master.zip
```

Note that another part of the workaround is to copy the missing `libarm_cortexM7lfsp_math.a` as instructed in https://github.com/platformio/platform-teensy/issues/51#issuecomment-679424383. This file is also contained in this repository for convenience. 
