# Boat Instrument

The instrument has in-app help accessible from the Settings Page.
Boxes that require more complex configuration have help accessible from their configuration pages.

## Installation

To install the Boat Instrument follow these [instructions](https://github.com/philseeley/boatinstrument/blob/main/install.md).

## Configuration

The configuration is stored in JSON format in the "boatinstrument.json" file.
This can be exported and imported from the Settings Page. Its on disk location depends upon the OS being used.

- **Android:** <storage\>/Android/data/name.seeley.phil.boatinstrument/files/boatinstrument.json
- **Linux:** $HOME/Documents/boatinstrument.json
- **MacOS:** $HOME/Library/Containers/name.seeley.phil.boatinstrument/Data/Documents/boatinstrument.json
- **Windows:** %UserProfile%/\<My Documents\>/boatinstrument.json
- **Flutter-pi:** /boatinstrument.json

**Note:** before starting on flutter-pi installs, if "/boot/boatinstrument.json" exists it is moved to "/boatinstrument.json" and if "/boot/boatinstrument.config" exists it is moved to "/etc/boatinstrument-fpi/config".

This allows you to update the configuration on a minimal OS via the SD Card, e.g. one without SSH or other access.

If you exit the instrument (from the Settings Page) the configuration file is copied to "/boot/boatinstrument.json.running". The instrument is then restarted.

If required, the config can be manually edited. This is easier if it is reformatted with:

```shell
python3 -m json.tool boatinstrument.json >boatinstrument-formatted.json
```

If the "--enable-set-time" command line option is given, e.g. in "/etc/boatinstrument-fpi/config", then you can set the Operating System time from the "navigation.datetime" path by enabling "Set Time" in the Advanced Settings.

## Box Path Mapping

When a page is displayed, the Boxes register the paths they require. After consolidation to remove any duplicates, the app then subscribes to these via a SignalK WebSocket.

The current list of subscriptions being used by the app can be viewed from the Settings page.

This is list of [Box to Path Mappings](box-path-mappings.md).

## Known Issued and Workarounds

### Linux and IPv6

The **Service Discovery** API on Linux returns IP addresses, whereas the other OSs return hostnames. This causes issues if your SignalK host has an IPv6 address, as the API may return this without the **Scpoe ID** suffix. This causes the connection to fail.

The simple fix is to disable IPv6 on your SignalK host using the NetworkManger, e.g. nmtui.

If you leave it enabled, then to connection will likely succeeded after some failed attempts as the **Service Discovery** will eventually return the IPv4 address.

If you need to use IPv6 addresses for your SignalK server, then explicitly specify the required URL, including the local **Scope ID/Interface Name**, e.g. "http://[fe80::bf92:7cd4:fbb:1234%wlp1s0]:3000"

### Starlink Box

Full functionality requires the acceptance of [this](https://github.com/itemir/signalk-starlink/pull/5) pull request to the **signalk-starlink** plugin.

### Auth Token Migration ###

Previous to version 3 of the config settings, authentication was stored on a Box Type basis. This allowed different Boxes to have different levels of authentication. From App version 0.8.0, when Remote Control functionality was introduced, the main App needed authentication. So authentication was simplified and moved to a single "Auth Token" at the App level.

The migration to the v3 config attempts to pick the best "Auth Token" from any already in the config and favoured the Box that required the highest level, i.e. the Anchor Alarm.

The issue that can arise, is that the user may have deleted that device from the SignalK security settings. This results in the following rather cryptic exception when connecting:
```
WebSocketChannelException: WebSocketException: Connection to 'http://signalk-server:3000/signalk/v1/stream?subscribe=none#' was not upgraded to websocket, HTTP status code: 401

```
This can be fixed by either deleting the "Auth Token" or requesting a new one with the required access level.