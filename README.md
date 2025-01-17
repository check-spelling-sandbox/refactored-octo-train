# release-downloader

Action to download and optionally extract binaries from GitHub releases.

## Usage

```yaml
- uses: ...
  with:
    # Repository name. For example cli/cli
    # Default: ${{ github.repository }}
    repository: ''

    # Path to place file(s)
    # Default: ${{ github.workspace }}
    destination: ''

    # Pattern to select file from within the archive
    # If omitted, the entire archive is extracted
    # Default: none
    file-re: ''

    # Release version
    # Default: latest
    version: ''

    # OS to use to filter artifacts
    # Default: current OS
    os: ''

    # OS pattern to filter artifacts
    # Default: pattern based on ${{ inputs.os }}
    os-pattern: ''

    # Architecture to use to filter artifacts
    # Default: current Architecture
    arch: ''

    # Architecture pattern to filter artifacts
    # Default: pattern based on ${{ inputs.arch }}
    arch-pattern: ''

    # Personal access token (PAT) used to fetch the repository.
    # Default: ${{ github.token }}
    token: ''

    # Debug action. Set to a value to trace action
    # Default: ''
    debug:
```

## Outputs

### path

The location of the extracted item(s).

### url

The url of the downloaded artifact.

## Recommended permissions

This action doesn't need access to your repository to perform its action, so if
your workflow is self contained and itself doesn't need anything from the repository,
you could probably use:

```yaml
permisions: {}
```

If you're retrieving an artifact from your repository and the repository itself is not public and you aren't providing a `token`, you'd need:

```yaml
permissions:
  contents: read
```

Obviously, if your workflow is nontrivial, you may need more permissions for other steps.
