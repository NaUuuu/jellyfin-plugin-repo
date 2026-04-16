# Jellyfin Plugin Repository

Auto-built Jellyfin plugins via GitHub Actions.

## Plugins

| Plugin | Upstream | Description |
|--------|----------|-------------|
| StrmTool | [jinlin-teck/StrmTool (jellyfin branch)](https://github.com/jinlin-teck/StrmTool/tree/jellyfin) | Extract media info from strm files to speed up playback |

## Usage

In Jellyfin: **Dashboard → Plugins → Repositories → Add** and paste the `manifest.json` raw URL of this repository.

## Build Process

The workflow runs daily and on manual trigger. For each run it:

1. Checks the latest commit SHA of the upstream `jellyfin` branch
2. Compares against `.last-build-sha` in this repo
3. If new, checks out the upstream source, builds with .NET 8, packages the DLL as a zip
4. Creates a GitHub Release with the zip
5. Updates `manifest.json` and commits

## Manual Build (optional)

If you want to build the DLL yourself:

```bash
# Requires .NET 8 SDK
git clone -b jellyfin https://github.com/jinlin-teck/StrmTool.git
cd StrmTool
dotnet publish StrmTool.csproj -c Release -o ./out
# DLL: ./out/StrmTool.dll
```
