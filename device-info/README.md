# Balena Device Info

This project provides a visual interface displaying basic device statistics.

## Example:

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
