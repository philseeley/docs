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

**Note:** before starting on flutter-pi installs, if "/boot/boatinstrument.json" exists it is moved to "/boatinstrument.json" and if "/boot/boatinstrument.config" exists it is moved to "/boot/boatinstrument.config".

This allows you to update the configuration on a minimal OS via the SD Card, e.g. one without SSH or other access.

If you exit the instrument (from the Settings Page) the configuration file is copied to "/boot/boatinstrument.json.running". The instrument is then restarted.

If required, the config can be manually edited. This is easier if it is reformatted with:

```shell
python3 -m json.tool boatinstrument.json >boatinstrument-formatted.json
```
## Box Path Mapping

When a page is displayed, the Boxes register the paths they require. After consolidation to remove any duplicates, the app then subscribes to these via a SignalK WebSocket.

The current list of subscriptions being used by the app can be viewed from the Settings page.

This is list of [Box to Path Mappings](box-path-mappings.md).