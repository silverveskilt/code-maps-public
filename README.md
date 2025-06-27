# CodeMaps - Code Structure Visualizer Tool

Welcome to CodeMaps! Gain better control over your software by visualizing the code structure and relationships between classes and methods in your project.

Disclaimer: CodeMaps **is not** an open-source project. This repository simply hosts a built version for public testing.

## Quick Start

### 1. Access the Web Interface
Open your browser and go to: **https://codemaps.silverveskilt.com**.

### 2. Start the local server
The CodeMaps uses a local http server to allow the web interface to access files on your system. Use your Docker environment to run it on your local machine using one of the following methods:

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

## Motivation

I was looking for a graphic tool to help me understand the dependencies and spot inefficiencies in the growing codebase of my Unity game project. After one of the Cursor plugins that I tested that was charging around $15 a month turned out to be another AI chatbot, and a second one didn't even start, I decided to give it a go and make one that solves the problem for me.

## Next steps

- Ship as standalone application for macOS
- Add Typescript parser
- Enable visualizing loosely coupled systems
- Ship as a plugin for Cursor and VSCode  
- Have a new idea how to make this tool more useful to you? 👇

## Support

For issues and questions:
- Reach out on https://www.linkedin.com/in/silverveskilt/ or to my email silverveskilt@gmail.com
- Open an issue in this github space
