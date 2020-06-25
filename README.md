<h1 align="center"> Octobalena</h1><br>
  <p align="center" >
  <img align="center" src="https://user-images.githubusercontent.com/26458780/69140128-cba46e80-0ab9-11ea-8980-075f71039643.png">
  <br><br>
</p>

Remotely control your 3d-printer with [octoprint](https://github.com/foosel/OctoPrint) + [octodash](https://github.com/UnchartedBull/OctoDash) via balena.io !

**octoprint can be exposed on port 80 which can be remotely accessible via balena.io [public URL](https://docs.balena.io/management/devices/#enable-public-device-url) feature**

By default, the device can be reached at `octobalena.local` if mDNS is working on your device.

# Configure via [environment variables](https://docs.resin.io/management/env-vars/)

## Octoprint Service Variables
Variable Name | Value | Description | Default
------------ | ------------- | ------------- | -------------
**`CAMERA_DEV`** | `STRING` | The camera device node | /dev/video0
**`MJPEG_STREAMER_AUTOSTART 	`** | `BOOLEAN` | Start the camera automatically  | true
**`MJPEG_STREAMER_INPUT`** | `STRING` | Flags to pass to mjpg_streamer | -y -n -r 640x480
**`MQTT_BROKER`** | `STRING` | Ip address of mqtt broker to use | 
**`MQTT_BROKER_PORT`** | `STRING` | Port the mqtt broker is running on | 
**`ESPURNA_RELAY_NAME`** | `STRING` | Relay name (hostname) used by espurna at the root of topic. E.G ESPURNA-123456, [see documentation](https://github.com/xoseperez/espurna/wiki/Configuration#direct-http-settings-api)  | 

## Octodash Service Variables
Variable Name | Value | Description | Default
------------ | ------------- | ------------- | -------------
**`OCTOPRINT_APIKEY`** | `STRING` | Needed for OctoDash to interact with Octoprint | 
**`PRINTER_NAME`** | `STRING` | Name of the printer, as shows up in the bottom left of OctoDash  | Octobalena

## mdns-publisher Service Variables
Variable Name | Value | Description | Default
------------ | ------------- | ------------- | -------------
**`OCTOPRINT_HOSTNAME`** | `STRING` | Adds CNAME for mDNS so device is reachable at string.local | octobalena

## Getting started

### Via Balena Deploy

You can deploy this project to a new balenaCloud application in one click using the button below: 

[![](https://www.balena.io/deploy.png)](https://dashboard.balena-cloud.com/deploy)

### Via Balena-Cli

- Sign up on [balena.io](https://dashboard.balena.io/signup)
- go through the [getting started guide](https://balena.io/docs/learn/getting-started) and create a new application
- clone this repository to your local workspace
- Using [Balena CLI](https://www.balena.io/docs/reference/cli/), push the code with `balena push <application-name>`
- See the magic happening, your device is getting updated 🌟Over-The-Air🌟!

### Via Git

- Sign up on [balena.io](https://dashboard.balena.io/signup)
- go through the [getting started guide](https://balena.io/docs/learn/getting-started) and create a new application
- clone this repository to your local workspace
- add the _balena remote_ to your local workspace using the useful shortcut in the dashboard UI
- `git push balena master`
- see the magic happening, your device is getting updated Over-The-Air!

## Attribution

- This is in part based on excellent work done by the Balena.io team

@see: https://github.com/balena-io-playground/balena-octoprint
