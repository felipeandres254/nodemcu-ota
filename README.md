# IoT projects with NodeMCU

Base IoT framework fot NodeMCU.
Uses [MongooseOS](https://mongoose-os.com) and [AWS IoT](https://aws.amazon.com/iot).

## Build and installation

1. Setup your WiFi SSID and password in [mos.yml](./mos.yml).
   ```yaml
   config_schema:
     - ["wifi.sta.ssid", "WIFI_SSID"]
     - ["wifi.sta.pass", "WIFI_PASS"]
   ```

2. Run the following commands in a WSL environment
   ```sh
   $ mos build
   $ powershell.exe -File "scripts/install.ps1"
   ```

3. Run `mos build && scripts/install`

# Over-The-Air updates

To make an OTA update make sure the device is connected to WiFi and it's shadow is reporting correctly. Also, the configuration and certificates must be available in `devices` directory.

1. Edit the filesystem within `fs`. The first file to run is [`init.js`](./fs/init.js).

2. When you are ready, run `scripts/ota <name> --update`.

You can also provide a directory name within the examples folder to this command:

```sh
$ ./scripts/ota <name> --update <example>
```
