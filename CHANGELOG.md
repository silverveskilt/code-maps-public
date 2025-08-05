# Changelog

All notable changes to the Code Maps UI will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.1.0] - 2025-08-05
- More accurate Typescript parser

## [1.0.0] - 2025-07-15

### BREAKING
- Simplified the setup. The UI and API are both deployed by the same Docker container. Removed server configuration step.
- Graph data is stored in file system instead of browser storage. 

**MIGRATION**:

**Step 1**: Create a data directory on your disk with write permissions for the container
```bash
cd /path/to/your/project
mkdir -p .codemaps-data
chmod 755 .codemaps-data
```

**Step 2**: Update your docker config to attach a volume for graph data: `-v /path/to/your/project/data:/app/data`

**Step 3**: Copy the contents of `nodePositions` and `selectedFiles` from your browser's Local Storage into the `nodePositions.json` and `selectedFiles.json` respectively in your data directory, according to your new Docker config. 

**Step 4**: Rebuild and run the container!

## [0.2.0] - 2025-07-04

### Added
- **Inspect Mode**:

  Click "Inspect" button on any method to activate inspect mode. Highlights calls that lead up to the inspected method. 

## [0.1.0] - 2025-06-26

### Added
- Initial release of Code Maps UI
