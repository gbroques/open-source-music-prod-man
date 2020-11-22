# Open Source Music Production Manual

## Setup
1. Install a Linux-based Operating System (OS) such as [Ubuntu 20.04 LTS](https://releases.ubuntu.com/20.04/).
2. Install a low-latency kernel if you don't already have one. Some distros such as Ubuntu Studio already have one. To check this, run:

        $ uname -r ↵
        5.4.0-54-generic

    * If you see **generic**, then run:

          sudo apt-get install linux-lowlatency
    
    * Afterwards, verify you have a low-latency kernel installed by running:

          $ uname -r ↵
          5.4.0-54-lowlatency

3. Add your user to the `audio` group:

        sudo usermod -a -G audio <user>

4. Add [KXStudio Repositories](https://kx.studio/Repositories) by following the instructions on their website.

5. Update the list of available packages:

        sudo apt update

6. Install `ardour`, `zynaddsubfx`, `pulseaudio-module-jack`, and `qjackctl`:

        sudo apt install ardour zynaddsubfx pulseaudio-module-jack qjackctl

7. Ensure `/etc/security/limits.d/audio.conf` has the following limits, and if not then manually change them:

        @audio   -  rtprio     95
        @audio   -  memlock    unlimited

    * You can also verify this by running the following commands:

          $ ulimit -r ↵
          95
          $ ulimit -l ↵
          unlimited

8. Edit `/etc/pulse/default.pa` so pulseaudio starts JACK by loading the `module-jack-sink` and `module-jack-source` modules:

        ### Load audio drivers statically
        ### (it's probably better to not load these drivers manually, but         instead
        ### use module-udev-detect -- see below -- for doing this         automatically)
        #load-module module-alsa-sink
        #load-module module-alsa-source device=hw:1,0
        #load-module module-oss device="/dev/dsp" sink_name=output         source_name=input
        #load-module module-oss-mmap device="/dev/dsp" sink_name=output         source_name=input
        #load-module module-null-sink
        #load-module module-pipe-sink
        load-module module-jack-sink
        load-module module-jack-source

9. Run `qjackctl` and start the JACK server. If pulseaudio is running, then the JACK server may not be able to start.

    * Verify pulseaudio is running:

          $ pulseaudio --check ↵
          $ echo $? ↵
          0

    * Suspend pulseaudio until `qjackctl` starts:
        
          pasuspender qjackctl

10. Verify everything is setup correctly by starting a new Ardour session with JACK and ALSA.
