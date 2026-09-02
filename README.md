# API-Example

A demonstration repository showing how to automate mod uploads to [NexusMods](https://www.nexusmods.com/) using GitHub Actions.

## Overview

This repository provides a working example of the [Nexus-Mods/upload-action](https://github.com/Nexus-Mods/upload-action) GitHub Action. It demonstrates how to set up automated workflows that package and upload mods to NexusMods whenever you trigger the workflow.

## How It Works

The workflow in `.github/workflows/upload-mod.yaml`:

1. Checks out the repository (with full history so the changelog can be built)
2. Generates a changelog from the current date and the 10 most recent commits
3. Zips the contents of the `src/` directory
4. Uploads the zip file to NexusMods using their API, including the generated changelog for the version

## Setup

To use this workflow in your own project, you'll need to configure the following:

### Secrets

- `NEXUSMODS_API_KEY` - Your NexusMods API key

### Variables

- `NEXUSMODS_FILE_ID` - The File ID for your mod on NexusMods
- `NEXUSMODS_MOD_ID` - The Mod ID for your mod on NexusMods (required to add a changelog)

## Usage

1. Copy `.github/workflows/upload-mod.yaml` to your own repository
2. Modify the workflow to zip your mod files (update the `zip` command as needed)
3. Configure the required secrets and variables in your repository settings
4. Trigger the workflow using one of the following methods:
   - **Create a release** - The workflow runs automatically and uses the release tag as the version
   - **Manual trigger** - Go to the Actions tab, select the workflow, and enter a version number

   In both cases the changelog is generated automatically from the current date and recent commits.

## License

MIT License - see [LICENSE](LICENSE) for details.
