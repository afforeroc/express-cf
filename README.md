# Create and configure an Express app to deploy on Cloud Foundry
> This repository has a web app sample with all necessary files to deploy it on cloud
>  * If you want to run it locally, you should review steps 1 and 2
>  * If you want to deploy it on cloud, you should review step 3
  
## Required software
* Command prompt like `Terminal`/`PowerShell`
* Text editor like `Notepad++`/`Visual Studio Code`

## Instructions

### 1. Install Node JS and Express
  1.1 Install the stable/latest version of [Node.js](https://nodejs.org/en/)

  1.2 Verify the Node JS installation
  ```
  node --version
  ```
  ```
  npm --version
  ```

  1.3 Install and verify the framework
  ```
  npm install express-generator -g
  ```
  ```
  express --version
  ```

  > If you can't see the framework version on Windows, launch a PowerShell window as an administrator and enter this following command. Later, try again to verify
  ```
  Set-ExecutionPolicy Unrestricted
  ```

### 2. Create and run the app
  2.1 Create the app
  ```
  express --view=pug express-app
  ```

  2.2 Access the root folder of app and install all necessary libraries
  ```
  cd express-app
  ```
  ```
  npm install
  ```

  2.3 Run the app. Later, open your favorite web browser on `localhost:3000`
  > Remember give access to Node.js to use the local network 
  ```
  npm start
  ```

  2.4 Stop the app with <kbd>ctrl</kbd> + <kbd>C</kbd>
  

### 3. Configure the app to deploy
  3.1 Go to the root folder `express-app\` and create `manifest.yml` file and edit it with following template
  ```
  ---
  applications:
  - name: express-app-<initials>-<date>
    memory: 64M
  ```

  3.2 Edit `manifest.yml` file changing the value of `- name` atribute. The name that should be **unique** because it will used as part of url of app. You can use the previous template putting your initials and the today's date.

## Reference links
* Cloudant Node.js Client: https://github.com/cloudant/nodejs-cloudant

## Information links
* Express page: https://expressjs.com/
* Express Generator page: https://expressjs.com/es/starter/generator.html
* Cloud Foundry Documentation: https://docs.cloudfoundry.org/ 
* Deploying with App Manifests: https://docs.cloudfoundry.org/devguide/deploy-apps/manifest.html