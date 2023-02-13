# File Manager

Provides a UI for uploading, modifying and removing files from a device.

## Example:

```dockerfile
version: "2"

services:
  balena-starter-interface:
    image: bh.cr/bdi/file-manager
    restart: always
    volumes:
      - "bdi_storage:/app/storage" # Storage for the File Manager. Add in a named volume of your choice.
    ports:
      - "80:80"
    labels:
      io.balena.features.supervisor-api: 1
      io.balena.features.balena-api: 1

volumes:
  bdi_storage:
```
