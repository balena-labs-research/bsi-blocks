# File Manager

<img width="1159" alt="file-manager" src="https://user-images.githubusercontent.com/64841595/219017075-65612229-1be4-4cd2-9e37-0a4724f7e41f.png">

---

Provides a UI for uploading, modifying and removing files from a volume.

Replace the `bdi_storage` volume in the example Dockerfile below with the name of the volume you would like to be visible in the File Manager.

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
