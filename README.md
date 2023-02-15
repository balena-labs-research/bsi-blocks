# Starter Interface Blocks

This repository contains the components for deploying the [balena Starter Interface](https://github.com/balena-labs-research/starter-interface) as independent Blocks.

Each block is stored inside its own folder, and deploy by GitHub Workflows to the Hub.

To add projects, copy the contents of the folder `template` in to a new folder for your project. Amend each of the files inside accordingly. Then copy `deploy-to-balena.yml` in to `.github/workflows/` and amend the file name and contents according to the project name.
