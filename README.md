# CodeMaps - C# Code Structure Visualizer

Welcome to CodeMaps! This tool helps you visualize the structure and relationships of your C# code files.

## Quick Start

### 1. Access the Web Interface
Open your browser and go to: **https://codemaps.silverveskilt.com**

### 2. Start the local server
The CodeMaps server runs locally to allow the web interface to access files on your system. Choose one of these methods from the Examples block below.

### 3. Connect and Analyze

1. **In the web interface**, click "Configure Server"
2. **Set the server URL** to: `http://localhost:3001`
3. **Test the connection** - it should show "Connected"
4. **Browse the files** in the working directory in the file browser
5. **Select your C# files** and click "View Graph"

## Examples

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

## Features

- **C# File Analysis**: Parses C# source files to extract classes, methods, and properties
- **Dependencies Between Classes**: Visualizes relationships and dependencies between different classes in your codebase
- **Method Invocation Sequence**: Provides an overview of the sequence of method calls and invocations throughout your code

## Security Notes

- Files are mounted as **read-only** for security
- The server only accesses files within the mounted directory
- No code is uploaded to external servers - all processing happens locally

## Support

For issues and questions:
- Check the [GitHub repository](https://github.com/your-username/code-maps)
- Open an issue for bugs or feature requests
