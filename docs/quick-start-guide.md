# Quick Start Guide - Diablo 4 Build Tool

## Immediate Next Steps

### 1. Examine Your JSON Data
Before we start coding, we need to understand the data structure:

- **Locate your JSON file(s)** containing Diablo 4 data
- **Open and examine** the structure - what fields are available?
- **Document key data types** like skills, items, stats, etc.
- **Identify relationships** between different data elements

### 2. Set Up Development Environment
Install the necessary tools:

```bash
# Install Node.js (if not already installed)
# Download from: https://nodejs.org/

# Verify installation
node --version
npm --version

# Install Electron globally (optional, for CLI tools)
npm install -g electron
```

### 3. Initialize Project
```bash
# Navigate to your project directory
cd d4-tool

# Initialize npm project
npm init -y

# Install Electron and development dependencies
npm install --save-dev electron electron-builder
npm install --save-dev concurrently wait-on cross-env
npm install --save-dev nodemon electron-reload

# Install additional dependencies for development
npm install --save-dev @types/node typescript
```

### 4. Create Basic Project Structure
```bash
# Create directory structure
mkdir src
mkdir src/main
mkdir src/renderer
mkdir src/shared
mkdir assets
mkdir data
mkdir dist
```

### 5. Create Initial Files

#### package.json Scripts
Add these scripts to your `package.json`:

```json
{
  "scripts": {
    "start": "electron .",
    "dev": "concurrently \"npm run watch\" \"wait-on http://localhost:3000 && electron .\"",
    "watch": "nodemon --watch src --exec \"npm run build\"",
    "build": "tsc",
    "dist": "electron-builder"
  }
}
```

#### Basic Electron Main Process
Create `src/main/main.js`:

```javascript
const { app, BrowserWindow } = require('electron');
const path = require('path');

function createWindow() {
  const mainWindow = new BrowserWindow({
    width: 1200,
    height: 800,
    webPreferences: {
      nodeIntegration: false,
      contextIsolation: true,
      enableRemoteModule: false,
      preload: path.join(__dirname, 'preload.js')
    }
  });

  mainWindow.loadFile('src/renderer/index.html');
  
  // Open DevTools in development
  if (process.env.NODE_ENV === 'development') {
    mainWindow.webContents.openDevTools();
  }
}

app.whenReady().then(createWindow);

app.on('window-all-closed', () => {
  if (process.platform !== 'darwin') {
    app.quit();
  }
});

app.on('activate', () => {
  if (BrowserWindow.getAllWindows().length === 0) {
    createWindow();
  }
});
```

#### Basic HTML Renderer
Create `src/renderer/index.html`:

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Diablo 4 Build Tool</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div id="app">
        <header>
            <h1>Diablo 4 Build Tool</h1>
        </header>
        <main>
            <div id="content">
                <p>Welcome to the Diablo 4 Build Tool!</p>
                <p>This is where your build creation interface will go.</p>
            </div>
        </main>
    </div>
    <script src="renderer.js"></script>
</body>
</html>
```

#### Basic CSS
Create `src/renderer/styles.css`:

```css
body {
    margin: 0;
    padding: 0;
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
    background-color: #1a1a1a;
    color: #ffffff;
}

#app {
    min-height: 100vh;
}

header {
    background-color: #2d2d2d;
    padding: 1rem;
    border-bottom: 2px solid #4a4a4a;
}

header h1 {
    margin: 0;
    color: #ffd700;
    text-align: center;
}

main {
    padding: 2rem;
}

#content {
    text-align: center;
    padding: 2rem;
}

#content p {
    margin: 1rem 0;
    font-size: 1.1rem;
}
```

#### Basic Renderer Script
Create `src/renderer/renderer.js`:

```javascript
// This is where your UI logic will go
console.log('Diablo 4 Build Tool - Renderer process loaded');

// Example: Add some basic interactivity
document.addEventListener('DOMContentLoaded', () => {
    console.log('DOM loaded, ready to initialize UI components');
    
    // This is where you'll add your UI initialization code
    // For now, just add a simple click handler
    const content = document.getElementById('content');
    content.addEventListener('click', () => {
        alert('UI is working! Time to build some features.');
    });
});
```

### 6. Test Your Setup
```bash
# Start the application
npm start
```

You should see a basic Electron window with your HTML content!

### 7. Next Development Steps

Once the basic app is running:

1. **Study the JSON data structure** - understand what you're working with
2. **Plan your data models** - design the interfaces for your data
3. **Start with a simple feature** - maybe just displaying character classes
4. **Build incrementally** - add one feature at a time
5. **Test frequently** - make sure each addition works before moving on

## Learning Resources

### Electron Basics
- [Electron Quick Start](https://www.electronjs.org/docs/tutorial/quick-start)
- [Main vs Renderer Process](https://www.electronjs.org/docs/tutorial/application-architecture)
- [IPC Communication](https://www.electronjs.org/docs/tutorial/ipc)

### Development Tools
- [VS Code Electron Debugging](https://code.visualstudio.com/docs/nodejs/nodejs-debugging)
- [Electron DevTools](https://www.electronjs.org/docs/tutorial/devtools-extension)

### Best Practices
- [Security Best Practices](https://www.electronjs.org/docs/tutorial/security)
- [Performance Best Practices](https://www.electronjs.org/docs/tutorial/performance)

## Common Issues & Solutions

### App Won't Start
- Check that all dependencies are installed
- Verify file paths in your main process
- Check console for error messages

### Changes Not Reflecting
- Make sure you're running the right script
- Check that file paths are correct
- Restart the app after major changes

### Performance Issues
- Start with small datasets
- Implement lazy loading early
- Monitor memory usage during development

---

**Ready to start coding?** Begin with examining your JSON data, then set up the basic project structure above. Once you have the basic app running, we can start building the actual features!

Remember: Start simple, test often, and don't be afraid to refactor as you learn more about what you're building.
