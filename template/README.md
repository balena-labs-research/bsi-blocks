# Balena Project Template

This project provides...

## Example:

```dockerfile
version: "2"

services:
  balena-starter-interface:
    image: bh.cr/bdi/project-template
    restart: always
    ports:
      - "80:80"
    labels:
      io.balena.features.supervisor-api: 1
      io.balena.features.balena-api: 1
```
