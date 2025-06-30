[Firmware Upload](http://192.168.8.238/upload)

[PNG Upload](http://192.168.8.238/upng)
Note that there are several PNG images stored in the firmware:
* Boil 1st/1-01.png
* Boil 1st/2-01.png
* clock - select analog.png
* clock - select digital.png
* clock - select off.png
* error screen - add water.png
* error screen - Calibration in progress.png
* error screen - cannot turn wifi.png
* error screen - Downloading.png
* error screen - Enable Wireless.png
* error screen - kettle not connected to network.png
* error screen - Set clock.png
* error screen - Set confirm water.png
* error.png
* factory reset - cancel.png
* factory reset - select.png
* Finished.png
* gmenu - Calibration.png
* gmenu - clock.png
* gmenu - language.png
* gmenu - wireless.png
* Guide/1-01.png
* Guide/2-01.png
* Language/1-01.png
* Language/2-01.png
* Language/3-01.png
* Language/4-01.png
* Language/5-01.png
* Language/6-01.png
* Language/7-01.png
* menu - altitude.png
* menu - chime.png
* menu - general.png
* menu - guide.png
* menu - hold.png
* menu - pre-boil.png
* menu - schedule.png
* menu - units.png
* none.png
* none2.png
* Schedule/2-01.png
* Schedule/3-01.png
* Schedule/4-01.png
* Schedule/6-01.png
* WiFi/1-01.png
* WiFi/2-01.png

[View all CLI commands](http://192.168.8.238/cli?cmd=help)
The CLI endpoint allows the user to issue all the commands that are possible
via the UART console.
```
I (40797169) Cli: cmd len 4: 'help'
I (40797169) Cli: reset : reset
I (40797169) Cli: state : print state
I (40797169) Cli: statesave : save state after given time (ms)
I (40797179) Cli: prtsaved : print saved state
I (40797179) Cli: setstate : set state
I (40797179) Cli: ss : set state
I (40797189) Cli: shot : print screenshot
I (40797189) Cli: refresh : refresh gui
I (40797189) Cli: sleepms : sleep given time ms
I (40797199) Cli: setsetting : setsetting name integer_value
I (40797199) Cli: setsettingd : setsetting name double_value
I (40797209) Cli: setsettings : setsetting name string_value
I (40797209) Cli: setsettingb : setsetting name hexstring
I (40797219) Cli: clrsettings : delete all settings
I (40797219) Cli: prtsettings : print settings
I (40797219) Cli: prts : print settings
I (40797229) Cli: prtclock : print clock
I (40797229) Cli: setclock : setclock hour min [sec]
I (40797239) Cli: incclock : increment clock minutes
I (40797239) Cli: incticks : increase tick count
I (40797249) Cli: setanalog : set clock mode = analog
I (40797249) Cli: setdigital : set clock mode = digital
I (40797249) Cli: setaltitudem : set altitude settings
I (40797259) Cli: setaltitudef : set altitude settings
I (40797259) Cli: setunitsc : set units = c
I (40797269) Cli: setunitsf : set units = f
I (40797269) Cli: fwinfo : print firmware info
I (40797279) Cli: setpart : set boot parition name
I (40797279) Cli: eraseotherpart : erase non-current OTA part
I (40797289) Cli: heapprt : print heap info
I (40797289) Cli: lvglinfo : print lvgl mem use
I (40797289) Cli: lvglpon : enable lvgl alloc print
I (40797299) Cli: lvglpoff : disable lvgl alloc print
I (40797299) Cli: logprt : print small log
I (40797309) Cli: gpioset : gpioset * 1 or gpioset * 0
I (40797309) Cli: heaton : set GPIO HEAT High
I (40797309) Cli: heatoff : set GPIO HEAT Low
I (40797319) Cli: warmon : set GPIO WARM High
I (40797319) Cli: warmoff : set GPIO WARM Low
I (40797329) Cli: warmduty : enable WARM pwm using duty percent
I (40797329) Cli: rmtflt : set filter for rmt
I (40797339) Cli: pwmprt : print pwm regs
I (40797339) Cli: temp : print tempr min/max/av
I (40797349) Cli: tstprd : set tempr stat/notif period ms
I (40797349) Cli: buz : buz freq_hz duty_13_bit dur_ms  or buz sos - run buzzer
I (40797369) Cli: wifiprt : print WiFi config
I (40797369) Cli: wifierase : erase wifi sap config
I (40797369) Cli: wifisappw : enter/save wifi sap password
I (40797369) Cli: wifistapw : enter/save wifi sta password
I (40797379) Cli: wifistassid : enter/save wifi sta ssid [pw]
I (40797389) Cli: wifioff : turn wifi off
I (40797389) Cli: wifion : turn wifi on
I (40797389) Cli: wifisap : start wifi softap mode
I (40797389) Cli: wifista : start wifi station mode
I (40797399) Cli: provreset : reset WiFi config (forget AP)
I (40797399) Cli: mdns : start mdns
I (40797409) Cli: blesec : start ble security
I (40797409) Cli: bleen : enable/start BLE
I (40797409) Cli: bledis : disable/stop BLE
I (40797419) Cli: iot : test iot
I (40797419) Cli: httpdwn : httpdwn url : download file via HTTP and drop
I (40797429) Cli: httpfw : httpfw : download/install FW via HTTP
I (40797429) Cli: httptest : httptest : verify that HTTPS server follows rules
I (40797439) Cli: 1 : short press button 1
I (40797439) Cli: 1d : push button 1
I (40797469) Cli: 1u : release button 1
I (40797469) Cli: 2 : short press button 2
I (40797469) Cli: 2d : push button 2
I (40797479) Cli: 2u : release button 2
I (40797479) Cli: q : rotate dial left
I (40797479) Cli: w : rotate dial right
I (40797479) Cli: left : rotate dial left
I (40797479) Cli: right : rotate dial right
I (40797489) Cli: bc : print button click count
I (40797489) Cli: read_adc : read adc voltage
I (40797489) Cli: temp_offset : Read temperature offset
I (40797499) Cli: adcsamples : number of adc samples
I (40797499) Cli: set_period : set pwm period in seconds
I (40797509) Cli: max_duty : set triac max duty
I (40797509) Cli: min_duty : set triac min duty
```

[CLI : 2 (Short Press Button 2 - Main dial - Kettle On/Off) ](http://192.168.8.238/cli?cmd=2)
```
I (40878879) Cli: cmd len 1: '2'
I (40878879) Cli: command '2' ret 0
```

[CLI : State](http://192.168.8.238/cli?cmd=state)
```
I (40875509) Cli: cmd len 5: 'state'
I (40875509) Main: OTA vd 1 ldt 36286 ldr 7 dip 0 waitsec 0 numf 20 wgi 1 iot r 0
scrname=wnd
value=164
mode=S_Heat        # <-- Can be one of :
                   #     S_Off, S_StartupToTempr, S_StartupToMenu, S_StartupMenu,
                   #     S_Standby, S_Heat, S_HeatOff, S_Hold, S_NoWater, S_MenuExitToTempr,
                   #     S_Set_clock, S_OTA_Start, S_OTA_Abort, S_clocK_menu,
                   #     S_Calib_finish, S_Calib_aborted, S_Calib_Halted, S_Calib_Started, S_Check_Wireless_setup
tempr=72.938158 C
temprB=100.000000 C
temprT=82.000000 C
ketl= ho 0 wd 0 nw 0 ipb 0 bf 0 tr 0
temps=164 2C
tempsc=192 2C
units=1
clock=10:14
ticks=40875509 40869019 40873824
ble conn=0
I (40875529) Cli: command 'state' ret 0
```

[CLI : Print Settings](http://192.168.8.238/cli?prtsettings)
```
I (41287769) Cli: cmd len 11: 'prtsettings'
prt_settings 0x3ffc58d4
st: clockmode=1
st: altitude=0 m
st: settempr=164 2C (82.000000 C 179.600006 F)
st: hold=0
st: chime=5
st: units=1
st: boil=0
st: guide=1
st: language=0
st: schedon=0
st: schtime=0:0
st: schtempr=0 F (-17.777779 C 0.000000 F)
st: wifimode=4
st: wificoun=0
st: wifiwascn=1223704966
st: bledis=0
st: blesec=0
st: dwnfc=0
st: instfc=0
st: offset_temp=1802383
st: bricky=0
st: Repeat_sched=0
settings print end
I (41287799) Cli: command 'prtsettings' ret 0
```
