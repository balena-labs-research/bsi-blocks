# Python WiFi Connect UI

<img width="650" alt="wifi" src="https://user-images.githubusercontent.com/64841595/219017082-ec24ef4f-91ca-4f31-9352-8941599fc415.png">

---

This project provides Python Wifi Connect and a captive portal through a user interface. Your device will create a hotspot and provide a captive portal for connecting to a nearby WiFi network when new devices connect.

It uses the [Python Wifi Connect](https://github.com/balena-labs-research/python-wifi-connect) project as a backend.

## Implementation

### Try it out

You can deploy the project to your device with the `Deploy` button [on the Hub](https://hub.balena.io/organizations/bdi/apps/python-wifi-connect-ui).

#### Optional Environment Variables

```
PWC_HOTSPOT_SSID: "Python WiFi-Connect" # Name as it appears in list of WiFi networks
PWC_HOTSPOT_PASSWORD: "balena01" # Optional. Must be 8 characters or more
```

### Add to existing projects

Alternatively, you can integrate it in to existing projects by adding the following to your `docker-compose.yml` file:

```yaml
version: "2"

services:
  balena-starter-interface:
    image: ghcr.io/balena-labs-research/bsi-pwc-block:latest
    restart: always
    ports:
      - "80:80"
    labels:
      io.balena.features.supervisor-api: 1
      io.balena.features.balena-api: 1

  python-wifi-connect:
    image: ghcr.io/balena-labs-research/python-wifi-connect:latest
    environment:
      # Hotspot details
      PWC_HOTSPOT_SSID: "Python WiFi Connect" # Name as it appears in list of WiFi networks
      # PWC_HOTSPOT_PASSWORD: "balena01" # Optional. Must be 8 characters or more

      # Required system variables
      DBUS_SYSTEM_BUS_ADDRESS: "unix:path=/host/run/dbus/system_bus_socket"
    network_mode: "host"
    restart: always
    volumes:
      - "pwc_db:/app/db" # Optional if not setting the hotspot SSID and password via the API
    labels:
      io.balena.features.dbus: "1"
    cap_add:
      - NET_ADMIN
    privileged: true # This can be removed if you do not need the LED connectivity indicator.

volumes:
  pwc_db:
```

## Advanced Configuration

[See the Python WiFi Connect project for more info](https://github.com/balena-labs-research/python-wifi-connect)
