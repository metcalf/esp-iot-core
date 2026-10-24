# esp-iot-core

Shared ESP-IDF network stack: Wi-Fi station management, HTTPS OTA, remote UDP logging,
an MQTT client base (`BaseMqttClient`) and a scheduler for periodic network tasks with a
connectivity watchdog (`NetworkTaskManager`). `Fake*` classes build on the host for unit tests.

Extracted from [hvac_control](https://github.com/metcalf/hvac_control) with history.

## Use
Add as a submodule under a project's components directory; the directory name is the
IDF component name, so consumers `REQUIRES esp-iot-core`:
`git submodule add git@github.com:metcalf/esp-iot-core.git components/esp-iot-core`.

Per checkout:
- Copy `include/wifi_credentials.h.example` to `include/wifi_credentials.h` and fill it in.
- For OTA releases, put `user@host` in `remote_spec.cfg` and run `release.sh` from the
  IDF project root. Set `OTA_DIR_PREFIX` (default `hvac_control_`) to match the OTA URL
  template.
