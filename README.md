# API-Example

A demonstration repository showing how to automate mod uploads to [NexusMods](https://www.nexusmods.com/) using GitHub Actions.

## Overview

This repository provides a working example of the [Nexus-Mods/upload-action](https://github.com/Nexus-Mods/upload-action) GitHub Action. It demonstrates how to set up automated workflows that package and upload mods to NexusMods whenever you trigger the workflow.

## How It Works

The workflow in `.github/workflows/upload-mod.yaml`:

1. Checks out the repository
2. Zips the contents of the `src/` directory
3. Uploads the zip file to NexusMods using their API

## Setup

To use this workflow in your own project, you'll need to configure the following:

### Secrets

- `NEXUSMODS_API_KEY` - Your NexusMods API key

### Variables

- `NEXUSMODS_MOD_ID` - The file ID for your mod on NexusMods
- `NEXUSMODS_GAME_DOMAIN` - The game domain name (e.g., `skyrimspecialedition`, `baldursgate3`)

## Usage

1. Copy `.github/workflows/upload-mod.yaml` to your own repository
2. Modify the workflow to zip your mod files (update the `zip` command as needed)
3. Configure the required secrets and variables in your repository settings
4. Trigger the workflow using one of the following methods:
   - **Create a release** - The workflow runs automatically and uses the release tag as the version
   - **Manual trigger** - Go to the Actions tab, select the workflow, and enter a version number

## License

MIT License - see [LICENSE](LICENSE) for details.
