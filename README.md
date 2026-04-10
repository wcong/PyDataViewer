# PyData Viewer

PyData Viewer adds a custom editor that renders Python data files inside VS Code. It uses a local Python interpreter to load the file and shows a structured tree plus a raw representation.

## Features

- Open supported Python data files in a custom editor view
- Tree view of the decoded data
- Raw repr view
- Refresh button to re-run the decode

## Requirements

- Python available on your PATH, or configure `pklviewer.pythonPath`

Security note: loading serialized data can execute code. Only open trusted files.

## Extension Settings

- `pklviewer.pythonPath`: Python executable used to decode data files (default: `python`)
- `pklviewer.condaPythonPath`: Absolute path to conda environment python (overrides `pklviewer.pythonPath`)
- `pklviewer.maxOutputBytes`: Maximum bytes of decoded JSON allowed from Python (default: 5242880)
- `pklviewer.maxDepth`: Maximum depth when expanding objects (default: 8)

## Build and install

1. Install dependencies: `npm install`
2. Build the extension: `npm run compile`
3. Package a VSIX: `npx @vscode/vsce package`
4. Install the VSIX: `code --install-extension pydata-viewer-0.0.1.vsix`

## Automated Builds and Downloads

This repository uses GitHub Actions to automatically build and package the VSIX file.

- **Latest Build**: Download the latest VSIX from the GitHub Actions artifacts (available for 90 days).
- **Releases**: For stable versions, create a GitHub Release to upload the VSIX.

To install from a downloaded VSIX: `code --install-extension path/to/pydata-viewer.vsix`

## Development

Press `F5` in VS Code to launch the extension host and open a workspace with supported files. Use the command `PyData Viewer: Open File` or open a supported file directly to use the custom editor.
