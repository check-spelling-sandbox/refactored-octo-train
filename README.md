# release-downloader

Action to download and optionally extract binaries from GitHub releases.

asdajhkjk

## Usage

```
uses: ...
with:
  repository: (defaults to current repository)
  file: (path to place file, defaults to working-directory)
  file-re: (pattern to select file from within the archive)
  version: (specify a specific release, defaults to latest)
  os: (OS for which to filter artifacts, defaults to current OS)
  os-pattern: (pattern to filter artifacts, defaults to patterns based on OS)
  arch: (Arch for which to filter artifacts, defaults to current Arch)
  arch-pattern: (pattern to filter artifacts, defaults to patterns based on Arch)
  token: (GitHub token to use to retrieve private artifacts, defaults to GitHub token)
  working-directory: (place to leave files if file isn't set, defaults to github workspace)
  debug: (set to a value to trace action, defaults to off)
```

## Outputs

### path

The location of the extracted item(s).

### url

The url of the downloaded artifact.
