# CodeMaps - Code Structure Visualizer Tool

Welcome to CodeMaps! This tool helps you visualize the structure and relationships of your software project.

Disclaimer: CodeMaps **is not** an open-source project. This repository simply hosts a production build as long as it's in the testing phase.

## Quick Start

### 1. Access the Web Interface
Open your browser and go to: **https://codemaps.silverveskilt.com**.

### 2. Start the local server
The CodeMaps uses a local http server to allow the web interface to access files on your system. To use it on your local machine, choose one of these methods from below.

### Analyze a Single Project
```bash
# Mount your project directory
docker run -p 3001:3001 -v /path/to/your/csharp/project:/app/code:ro silverveskilt/codemaps-server:latest
```

### Using docker-compose
```yaml
# docker-compose.yml
version: '3.8'
services:
  codemaps-server:
    image: silverveskilt/codemaps-server:latest
    ports:
      - "3001:3001"
    volumes:
      - /Users/username/Projects/MyCSharpApp:/app/code:ro  # Your actual path here
```

### 3. Connect and Analyze

1. **In the web interface**, click "Configure Server"
2. **Set the server URL** <code>http://localhost:3001</code>
3. **Test the connection** - it should show "Connected"
4. **Browse the files** in the working directory in the file browser
5. **Select your files** and click "View Graph"


## Features

- **File Analysis**: Parses source files to extract classes, methods, and properties
- **Dependencies Between Classes and methods**: Visualizes relationships and dependencies between different classes in your codebase

## Security Notes

- Files are mounted as **read-only** for security.
- The server only accesses files within the mounted directory
- CodeMaps has no central server or database and no files are uploaded to external servers - all processing happens locally
- Only use if you trust the developer

## Next steps

- Ship as standalone application for macOS
- Add Typescript parser
- Enable visualizing loosely coupled systems
- Ship as a plugin for Cursor and VSCode  
- ...Feel free to get in touch with your ideas 👇

## Support

For issues and questions:
- Reach out on https://www.linkedin.com/in/silverveskilt/ or to my email silverveskilt@gmail.com
- Open an issue in this github space
