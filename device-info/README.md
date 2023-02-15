# Balena Device Info

<img width="1154" alt="device-info" src="https://user-images.githubusercontent.com/64841595/219017066-c4cdf5d3-4fb4-4564-9203-d65ef93af891.png">

---

This project provides a visual interface displaying basic device statistics.

## Example:

```dockerfile
version: "2"

services:
  balena-starter-interface:
    image: bh.cr/bdi/device-info
    restart: always
    ports:
      - "80:80"
    labels:
      io.balena.features.supervisor-api: 1
      io.balena.features.balena-api: 1
```
