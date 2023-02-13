# Environment Variable Configuration

Allows configuring on-device environment variables from a web interface.

## Example:

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
