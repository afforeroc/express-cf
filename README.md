# Create and configure an Express app to deploy on Cloud Foundry

**Note**: this repository has a Express app with all necessary files to deploy it on cloud, but it is necessary do the step 4.

## Required software
* Command prompt like `Terminal` or `PowerShell`
* Text editor like `Notepad++` or `Visual Studio Code`

### 1. Install Node.js and Express
* Install the latest version of [Node.js](https://nodejs.org/en/)

* Verify the Node.js installation
```
node --version
```

* Verify the NPM installation
```
npm --version
```

* Install the lastest version of Express Generator
```
npm install express-generator -g
```

* Verify the Express version
```
express --version
```

> If you can't see the Express version on PowerShell, launch a PowerShell window as an administrator and enter this command
```
Set-ExecutionPolicy Unrestricted
```
> and again verify the Express version

### 2. Create and check the app
* Create the app
```
express --view=pug express-app
```

* Access the root folder of app
```
cd express-app
```

* Install all necessary libraries
```
npm install
```

* Run the app. Later, open your favorite web browser on `localhost:3000` 
```
npm start
```
> Remember give access to Node.js to use the local network

* Stop the app with this combination keys
```
(Ctrl + C)
```

### 3. Configure the app to deploy
* Go to `express-app` folder and create `manifest.yml` file and edit it with following template
```
---
applications:
- name: express-app-<initials>-<date>
  memory: 64M
```

### 4. Put a name to your app
* Edit `manifest.yml` file changing the value of `- name` atribute. The name that should be **unique** because it will used as part of url of app. You can use the previous template putting your initials and the today's date.

## Reference links
* Cloudant Node.js Client: https://github.com/cloudant/nodejs-cloudant

## Information links
* Express page: https://expressjs.com/
* Express Generator page: https://expressjs.com/es/starter/generator.html
* Cloud Foundry Documentation: https://docs.cloudfoundry.org/ 
* Deploying with App Manifests: https://docs.cloudfoundry.org/devguide/deploy-apps/manifest.html