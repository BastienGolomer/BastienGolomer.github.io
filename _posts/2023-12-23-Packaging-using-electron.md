---
layout: post
title:  "How to package a simple destop app using electron!"
date:   2023-12-23 15:00:00 +0200
---

## Context

I was developping a simple todo list app to train in HTML, CSS and Javascript.

I had a `home.html`, a `styles.css` and a `scripts.js`, which made everything work once you open the html file in a browser.

I wanted to package this application. I asked [phind.com](https://phind.com) for help and here are the steps I followed and learnt. It uses Node.js and Electron.

## Steps for pacakging locally
To package an application consisting of an HTML file with JavaScript scripts and a CSS file, you can use a combination of Node.js and Electron. Here are the steps:

### Set Up Your Project Directory
Create a new directory for your project and navigate into it (I already had done this step). 
```bash
    mkdir my-app
    cd my-app
```

Initialize it as an npm package by running `npm init`. This will create a package.json file that stores metadata about your project and its dependencies 3.

### Install Electron
Install Electron as a development dependency in your project using the command `npm install --save-dev electron`. This will download all the necessary Node modules and add Electron as a development dependency in your package.json file.

Also, running this command will automatically guide you through the steps of creating a `package.json` file. I would advise you to just follow it if it is your first time like it was for me.


### Create Your HTML, CSS, and JavaScript Files
Create your HTML, CSS, and JavaScript files in your project directory. Make sure to link your CSS and JavaScript files correctly in your HTML file 1.

  <!DOCTYPE html>
  <html>
    <head>
      <meta charset="utf-8">
      <title>My App</title>
      <link rel="stylesheet" type="text/css" href="styles.css">
    </head>
    <body>
      <!-- Your HTML content -->
      <script src='script.js'></script>
    </body>
  </html>
**Note**: I had this step done.

### Create a Main Script
Create a main script (usually named `main.js`) in your project root. This script will start your application and create a new browser window to render your HTML file. The BrowserWindow object represents a window in Electron, and you can use it to control the window's behavior.
```javascript
  const { app, BrowserWindow } = require('electron')

  function createWindow () {
    let win = new BrowserWindow({
      width: 800,
      height: 600,
      webPreferences: {
        nodeIntegration: true,
      }
    })

    win.loadFile('index.html')
  }

  app.whenReady().then(createWindow)
```

### Update package.json
Update the package.json file to set the main field to main.js and add a start script to launch your application .
```json
  {
    "name": "my-app",
    "version": "1.0.0",
    "description": "",
    "main": "main.js",
    "scripts": {
      "start": "electron ."
    },
    "keywords": [],
    "author": "",
    "license": "ISC",
    "devDependencies": {
      "electron": "^x.y.z"
    }
  }
```
### Run Your Application
Run your application using the command `npm start`. This will start Electron and open a new window rendering your HTML file.

## Create a package for distribution 

### Install Electron Packager
Electron Packager is a command line tool that packages Electron apps for distribution. Install it as a dev dependency in your project using npm: `npm install electron-packager --save-dev`.

### Update package.json
Add a package script to your package.json file. This script will use Electron Packager to package your application for all platforms:
```json
 "scripts": {
   "package": "electron-packager . --platform=all --arch=all --out=release-builds"
 }
```

### Run the Package Script
Run the package script using `npm run package`. This command will create a new directory called release-builds in your project root directory. This directory will contain the packaged application for all platforms. 

**Note**: This command was long for me to run and my computer was not a fan (or was it?). I think this is one of the major complaints about using electron: you need to add the full framework for your application to run, even if the number of features used is limited (there is no light version).

### Distribute Your Application
**Note**: I haven't completed this step.
The packaged application can now be distributed to users. For example, you could create an installer for Windows using the NSIS tool or create a disk image for macOS using the hdiutil command. Alternatively, you could upload the packaged application to a distribution platform such as the Mac App Store or the Microsoft Store.

Remember, before distributing your application, it's highly recommended that you code sign your Electron app. Code signing is a security technology that you use to certify that a desktop app was created by a known source. Windows and macOS have their own OS-specific code signing systems that will make it difficult for users to download or launch unsigned applications 3.

Now, I wanted to publish my code on GitHub. My problem was, I didn't know what the best practices are for publishing such code. I asked the following question: 

"What are the best practices for publishing the app code on github. I mean, what should I put in my .gitignore?"

Here is the condensed version of the .gitignore file:
```git
node_modules/

.DS_Store
Thumbs.db

.env

release-builds/

.vscode/

ios/
```

And here are the explanations:
1. Node Modules: Since you're using Node.js, you should ignore the node_modules directory. This is where npm installs your project's dependencies. It's usually very large and doesn't need to be included in the repository. Instead, users can install the dependencies themselves by running npm install 5.
2. Operating System Specific Files: You should ignore operating system specific files like .DS_Store (macOS) and Thumbs.db (Windows). These files are generated automatically and don't need to be tracked 
3. Environment Variables: If you're using environment variables (like API keys), make sure to exclude them from your repository. They should be stored securely and not exposed publicly. You can ignore files containing sensitive data by creating a .env file and adding it to your .gitignore
4. Build Directories: If you're building your project (like transpiling TypeScript to JavaScript), you should ignore the build directories. These directories often contain compiled code and other intermediate files that aren't needed in the repository 
5. IDE Specific Files: Ignore files and directories created by IDEs. For instance, Visual Studio Code creates a .vscode directory to store workspace settings
6. Platform-Specific Files: If you're developing for specific platforms (like Android or iOS), you should ignore platform-specific files and directories. For example, the ios/ directory contains files specific to iOS development and should be ignored for a Node.js project.


## Conclusion
With this little experiment, I was able to package an application using node.js and electron and publish the code on github. The project is available at [todo_app](https://github.com/BastienGolomer/todo_app) and I might add other features to it in the future! Thank you for reading! 