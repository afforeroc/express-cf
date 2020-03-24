# Create and configure an Express app to deploy on Cloud Foundry
This repository has a README.md with instructions to create and configure an Express app to deploy on Cloud Foundry 
Also, here is an example of Express app with all files generated using the instrunctions.
* If you want to deploy it, but before that it is important to do step 4.

**Note 1** if you want deploy it this  but it is necessary do the step 4.
**Note 2** if

## Required software
* Command prompt like `Terminal` or `PowerShell`
* Text editor like `Notepad++` or `Visual Studio Code`

### 1. Install Node.js and Express
  1.1 Install the latest version of [Node.js](https://nodejs.org/en/)

  1.2 Verify the Node.js and NPM installation
  ```
  node --version
  ```
  ```
  npm --version
  ```

  1.3 Install Express Generator and verify the Express version
  ```
  npm install express-generator -g
  ```
  ```
  express --version
  ```

  > If you can't see the Express version on Windows, launch a PowerShell window as an administrator and enter this following command and again verify the Express version
  ```
  Set-ExecutionPolicy Unrestricted
  ```

### 2. Create and run the app
* 2.1 Create the app
```
express --view=pug express-app
```

* 2.2 Access the root folder of app and install all necessary libraries
```
cd express-app
```
```
npm install
```

* 2.3 Run the app. Later, open your favorite web browser on `localhost:3000`
> Remember give access to Node.js to use the local network 
```
npm start
```

* 2.4 Stop the app with this combination keys.
```
(Ctrl + C)
```

### 3. Configure the app to deploy
Go to `express-app` folder and create `manifest.yml` file and edit it with following template
```
---
applications:
- name: express-app-<initials>-<date>
  memory: 64M
```

### 4. Put a name to your app
Edit `manifest.yml` file changing the value of `- name` atribute. The name that should be **unique** because it will used as part of url of app. You can use the previous template putting your initials and the today's date.

## Reference links
* Cloudant Node.js Client: https://github.com/cloudant/nodejs-cloudant

## Information links
* Express page: https://expressjs.com/
* Express Generator page: https://expressjs.com/es/starter/generator.html
* Cloud Foundry Documentation: https://docs.cloudfoundry.org/ 
* Deploying with App Manifests: https://docs.cloudfoundry.org/devguide/deploy-apps/manifest.html