# Extism CLI Plugin for asdf and mise

A plugin for managing [Extism CLI](https://github.com/extism/cli) versions. This plugin is compatible with both [asdf](https://asdf-vm.com/) and [mise](https://mise.jdx.dev/).

## Features

- Direct binary downloads from GitHub releases.
- Full compatibility with asdf and mise (jdx) workflows.
- Automatic OS and architecture detection (macOS/Linux, amd64/arm64).

## Installation

### mise

```bash
mise plugin add extism https://github.com/jhovadev/asdf-extism.git
```

### asdf

```bash
asdf plugin add extism https://github.com/jhovadev/asdf-extism.git
```

## Usage

### Install Extism CLI

```bash
# mise
mise install extism@latest

# asdf
asdf install extism latest
```

### Set Version

```bash
# mise (global)
mise use -g extism@latest

# asdf (global)
asdf global extism latest
```

## Local Development

If you are contributing to this plugin or testing changes locally:

### mise

```bash
# Link current directory as a plugin
# Be careful: mise might expect the plugin name to match the repo or the logic.
# If you want to use it as 'extism', link it as such.
mise plugins link extism .

# Remove the link
mise plugins unlink extism
```

### asdf

```bash
# Manually symlink to the asdf plugins directory
ln -s "$(pwd)" "$ASDF_DIR/plugins/extism"
```

## Technical Details

The plugin implements the standard asdf interface:
- `bin/list-all`: Fetches available versions from the GitHub API.
- `bin/download`: Handles binary retrieval and extraction from GitHub releases.
- `bin/install`: Configures the binary in the tool execution path.

## License

MIT © [jhovadev](https://github.com/jhovadev)
