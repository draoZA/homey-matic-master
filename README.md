# Homematic

This app adds support for Homematic device in Homey via the CCU2/CCU3/RaspberryMatic

What works:

Devices can be connected via the following interfaces to the CCU:

* BidCos
* Homematic IP
* CUxD

## MQTT

As of 0.15.0 the app also supports the connection to the CCU via MQTT. This feature is currently cosidered experimental. The reason it is considered experimental is that it might be required to make some changes on the CCU in future versions of the app which could cause the app not to work until the changes are implemented.

It depends on RedMatic (Node Red) and Mosquitto (MQTT broker) to be configured on the CCU and therefore only supports the CCU3 ud RaspberryMatic.

The implementation is fully compatible with the existing devices that have been paired before it was enabled. It is also possible to switch back to the old mode without requiring to pair devices again.

MQTT is more stable than the connection via RPC as used otherwise. It also fixes the issue that some users have been experiencing where the devices stopped working after some time and a restart of the app was required to fix it. The performance is also increased which means that switch operations as executed faster and more reliable.

See the [Wiki](https://github.com/twendt/homey-matic/wiki/MQTT-Setup) for a detailed description on setting it up.

I recommend not to enable the auto update of this app in Homey and always check this page to make sure that no action is required before updating the app.

If you encounter any issues then please open an issue on GitHub.

If you have a device that is not supported currently then please open an issue on github and we will look into it.

The app uses discovery to find your CCUs on the network. We were only able to test it with a single CCU yet. Therefore it is possible that the app fails in case multiple CCUs are discovered on the network.

# Supported devices
* HM-CC-RT-DN
* HM-ES-PMSw1-DR
* HM-ES-PMSw1-Pl
* HM-ES-PMSw1-Pl-DN-R5
* HM-ES-TX-WM
* HM-LC-Bl1-FM
* HM-LC-Bl1PBU-FM
* HM-LC-Dim1PWM-CV
* HM-LC-Dim1T-CV
* HM-LC-Dim1T-DR
* HM-LC-Dim1T-FM
* HM-LC-Dim1TPBU-FM
* HM-LC-Sw1-Ba-PCB
* HM-LC-Sw1-DR
* HM-LC-Sw1-FM
* HM-LC-Sw1-Pl
* HM-LC-Sw1-Pl-2
* HM-LC-Sw1-Pl-CT-R1
* HM-LC-Sw1-Pl-DN-R1
* HM-LC-Sw1-Pl-DN-R5
* HM-LC-Sw1PBU-FM
* HM-LC-Sw2-FM
* HM-LC-Sw2PBU-FM
* HM-LC-Sw4-Ba-PCB
* HM-LC-Sw4-DR
* HM-LC-Sw4-DR-2
* HM-LC-Sw4-SM
* HM-LC-Sw4-WM
* HM-MOD-Re-8
* HM-OU-LED16
* HM-PB-2-FM
* HM-PB-2-WM55-2
* HM-PB-4-WM
* HM-PB-6-WM55
* HM-PBI-4-FM
* HM-RC-2-PBU-FM
* HM-RC-4
* HM-RC-4-2
* HM-RC-4-3
* HM-RC-8
* HM-RC-Key4-2
* HM-RC-Key4-3
* HM-RC-Sec4-3
* HM-SCI-3-FM
* HM-Sec-Key
* HM-Sec-MDIR-2
* HM-Sec-RHS
* HM-Sec-SC
* HM-Sec-SC-2
* HM-Sec-SCo
* HM-Sec-SD
* HM-Sec-SD-2
* HM-Sec-Sir-WM
* HM-Sec-WDS
* HM-Sec-WDS-2
* HM-Sen-DB-PCB
* HM-Sen-MDIR-O
* HM-Sen-MDIR-O-2
* HM-Sen-MDIR-O-3
* HM-Sen-MDIR-WM55
* HM-Sen-RD-O
* HM-SwI-3-FM
* HM-TC-IT-WM-W-EU
* HM-WDS10-TH-O
* HM-WDS100-C6-O
* HM-WDS30-T-O
* HM-WS550STH-I
* HMIP-PS
* HMIP-PSM
* HMIP-SWDO
* HMIP-WRC2
* HMIP-WTH
* HMIP-eTRV
* HmIP-ASIR
* HmIP-ASIR-2
* HmIP-BDT
* HmIP-BRA
* HmIP-BRC2
* HmIP-BROLL
* HmIP-BSM
* HmIP-BWTH
* HmIP-BWTH24
* HmIP-DRSI1
* HmIP-FCI1
* HmIP-FBL
* HmIP-FDT
* HmIP-FROLL
* HmIP-FSM
* HmIP-FSM16
* HmIP-MOD-HO
* HmIP-MOD-OC8
* HmIP-PCBS
* HmIP-PCBS-BAT
* HmIP-PS-CH
* HmIP-PS-PE
* HmIP-PS-UK
* HmIP-PSM-CH
* HmIP-RC8
* HmIP-SAM
* HmIP-SCI
* HmIP-SLO
* HmIP-SMI
* HmIP-SMI55
* HmIP-SMO
* HmIP-SMO-A
* HmIP-SPI
* HmIP-SRH
* HmIP-STE2-PCB
* HmIP-STH
* HmIP-STHD
* HmIP-STHO
* HmIP-SWD
* HmIP-SWDM
* HmIP-SWDO-I
* HmIP-SWDO-PL
* HmIP-SWO-PR
* HmIP-SWSD
* HmIP-WRC6
* HmIP-WTH-2
* HmIP-eTRV-2
* HmIP-eTRV-B
* HmIP-eTRV-C
* HmIP-eTRV-E

# Credits

Thank you [@hobbyquaker](https://github.com/hobbyquaker) for your great work on binrpc, xmlrpc, hm-discover and RedMatic.
This app was build by [@twendt](https://github.com/twendt). Great job. Thanks!

All code from [previous repository](https://github.com/twendt/homey-matic). So all credits should go to that team. Unfortunately @twendt stopped active development. There was a pull request that hadn't been actioned after 6 month. So I've decided to clone the repository and continue development here. Main goal to add a device or two that haven been recently added to the Homematic family but not to this app yet. Unfortunately I won't be able to continue full development and/or support. Anybody who wantsto contribute is welcome. If anybody wants to take over active development and host the repository, let me know.

# HOWTO

To use this app version you will need to install it via [developer access](https://apps.developer.homey.app/) to your homey. No worries, easier than it sounds :-) It will overwrite your existing Homematic app (backup before!) and keep all existing devices. Once installed the new device types are available to add. 

Everything on your own risk. So backup before! I won't be able to provide support.

1) Download Code: Select "CODE" here and get ZIP file
2) Enzip package on your local PC
3) Optional: Install Visual Studio Code (free)
4) Follow steps from[ Homey Dev Guide](https://apps.developer.homey.app/the-basics/getting-started)
  - Install Node
  - >>> Go to your unzipped files in command line/terminal window. Make sure you are in the homey-matic-master folder!
  - Install Homey CLI: npm install --global --no-optional homey
  - Skip the create app - as you already have one
  - Run the App to have it build and see if all connects: homey app run
  - If all looks good cancel run with CTRL-C
  - Install the App: homey app install

For questions post in the [Homematic App Forum @ Homey](https://community.homey.app/t/app-pro-homematic-app-v1-0-0-beta/1057).

# Change Log

## 0.20.0

Added devices:
* HmIP-SWDO-PL
* HmIP-eTRV-E

Removed XMLRPC and MQTT from connection options in settings. Connection will need to use CCUJack. CCUJack has to be installed as Add-on on CCU. CCUJack internally uses MQTT as well.


