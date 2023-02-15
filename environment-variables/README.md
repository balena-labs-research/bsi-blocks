# Environment Variable Configuration

<img width="1040" alt="env-config" src="https://user-images.githubusercontent.com/64841595/219017072-a52bd593-6d40-45a1-92d9-d20dcac2e97c.png">

---

Allows configuring on-device environment variables from a web interface. Requires your device to be connect to a balena Cloud fleet.

## Example:

```dockerfile
version: "2"

services:
  balena-starter-interface:
    image: bh.cr/bdi/environment-variables
    restart: always
    ports:
      - "80:80"
    labels:
      io.balena.features.supervisor-api: 1
      io.balena.features.balena-api: 1
```
