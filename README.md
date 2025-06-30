# Stagg EKG Pro
This project uses Python to communicate with the [Fellow Stagg EKG Pro]() over Wifi.

A lot of the information used to create this program came from [this post](https://www.reddit.com/r/homeassistant/comments/ek47k2/ble_reverse_engineering_a_fellow_stagg_ekg_kettle/) and additional testing I performed.

This is intended to be used with Homebridge and [my `homebridge-kettle` plugin](https://github.com/calvinmclean/homebridge-kettle).


## Getting Started
Currently, the only change that should be needed is changing the `MAC` variable in `api.py`. I plan to add something with a configuration file or environment variable to make this simpler.

Before running you will need to [install `bluepy`](https://github.com/IanHarvey/bluepy).


## Systemd
I run this on a Raspberry Pi alongside Homebridge, so I cloned this repo at `/root/stagg-ekg-plus` and setup this Systemd Service file to easily handle restarts and log to `syslog`:
```
[Unit]
Description=Python 3 API for Stagg EKG+
After=syslog.target network-online.target

[Service]
Type=simple
User=root
ExecStart=/usr/bin/python3 -u /root/stagg-ekg-plus/api.py
Restart=on-failure
RestartSec=10
KillMode=process
StandardOutput=syslog
StandardError=syslog

[Install]
WantedBy=multi-user.target
```

## More Info
These are some `gattool` commands that were really useful when figuring this stuff out:
```bash
gatttool -b $KETTLE_MAC -I
# connect, authenticate, and turn on then off
> connect
> char-write-cmd 0x000d efdd0b3031323334353637383930313
> char-write-cmd 0x000d efdd0a0000010100
> char-write-cmd 0x000d efdd0a0400000400

# subscribing
> char-write-req 0x000e 0100
> char-write-cmd 0x000d efdd0b3031323334353637383930313233349a6d
```

## HTTP endpoint
The Stagg EKG Pro presents an unsecured HTTP endpoint from which all CLI commands can be executed:
```bash
# Retrieve kettle state
$ http http://192.168.8.238/cli cmd==state --body
            <form action="cli" method="GET">
            <label for="x">CLI Command:</label><br>
            <input type="text" id="cli" name="cmd"><br>
            </form>
            I (35106409) Cli: cmd len 5: 'state'
I (35106419) Main: OTA vd 1 ldt 34485 ldr 7 dip 0 waitsec 1181 numf 19 wgi 1 iot r 0
scrname=wnd
value=50661414
mode=S_Off
tempr=27.433256 C
temprB=100.000000 C
temprT=93.000000 C
ketl= ho 0 wd 0 nw 0 ipb 0 bf 0 tr 0
temps=186 2C
tempsc=192 2C
units=1
clock=8:38
ticks=35106419 231639 35104734
ble conn=0
I (35106429) Cli: command 'state' ret 0

# Turn kettle heating on
$ http http://192.168.8.238/cli cmd==heaton --body
            <form action="cli" method="GET">
            <label for="x">CLI Command:</label><br>
            <input type="text" id="cli" name="cmd"><br>
            </form>
            I (35167439) Cli: cmd len 6: 'heaton'
I (35167439) Main: set HEAT High
I (35167439) Cli: command 'heaton' ret 0

# Turn kettle heating off
$ http http://192.168.8.238/cli cmd==heatoff --body
            <form action="cli" method="GET">
            <label for="x">CLI Command:</label><br>
            <input type="text" id="cli" name="cmd"><br>
            </form>
            I (35178399) Cli: cmd len 7: 'heatoff'
I (35178399) Main: set HEAT Low
I (35178399) Cli: command 'heatoff' ret 0
```
