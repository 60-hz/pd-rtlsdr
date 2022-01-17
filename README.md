pd-rtlsdr
=========

Pd external for rtl-SDR usb dongle.

RTL-SDR is a very cheap ~$25 USB dongle that can be used as a computer based radio scanner for receiving live radio signals in your area (no internet required). Depending on the particular model it could receive frequencies from 500 kHz up to 1.75 GHz. Most software for the RTL-SDR is also community developed, and provided free of charge. (from https://www.rtl-sdr.com/about-rtl-sdr/).

This is a pre-release version. Documentation is in progress. Here are couple of demo videos:

https://www.youtube.com/watch?v=m7SydPb6Ycs

http://youtu.be/MafEBdgM3E4


Note: You can only run one radio and one instance of the [rtlsdr~] object. This will be fixed in future releases. 

For more information about rtl-sdr: http://sdr.osmocom.org/trac/wiki/rtl-sdr


Quick-start:
====
the [rtlsdr~] object sends out raw IQ data from an rtlSDR device.

[rtlsdr~] responds to following messages:

start : start the radio

stop : stop the radio

freq [freq in Hz] [immediate (optional)] : set frequency in Hz. If immediate is set to 1 then frequency is changed immediately. Otherwise will take effect after start message.

gain [gain in dB] [immediate (optional)] : set RF gain. If immediate is set to 1 then gain is changed immediately. Otherwise will take effect after start message. Default is AUTO. Note: -10 will also set auto.

samplerate [samplerate] : set sample rate. Takes effect after start message. default is current Pd/Max sample rate.
	
Note that the example patches run inside block~ (pd) to allow higher sample rate for better wide band FM detection.

Pd MacOS:
====

Plug in your rtlSDR radio, run pure data.

Go to help -> find externals
Install cyclone externals
Install zexy externals

Open pd/macOS/bin/rtlSDR-block.pd with puredata
 
Then click the "start" message


Compiling from source:
====

Pd MacOS (64bit)
====

 Dependencies:

 brew install libusb-1.0

 brew install rtlsdr

Run the makefile inside src/macOS/ folder: sudo make


Acknowledgement:
====
I used vast amounts of code from rtl_fm by Kyle Keen, http://kmkeen.com/rtl-demod-guide/: rtl_fm is part of the rtl-sdr distribution.

linux build and Pd example patches developed by Katja Vetter

Many thanks to: Joseph Deken, and Fred Jan Kraan

New Blankets http://newblankets.org

Contact
====
Questions? Interested in helping out?

tkzic@megalink.net (Tom Zicarelli)
http://tomzicarelli.com

Updated by 60hz 2022

