# System Info

Fetch various system information, such as Journalctl logs, CPU and memory stats displayed through a web interface.

## Example:

```dockerfile
version: "2"

services:
  balena-starter-interface:
    image: bh.cr/bdi/system-info
    restart: always
    ports:
      - "80:80"
    labels:
      io.balena.features.supervisor-api: 1
      io.balena.features.balena-api: 1
```
