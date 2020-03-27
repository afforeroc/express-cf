# Create and configure a Express app to deploy on Cloud Foundry
This repository belongs to tutorial set of repository [Deploy a web application on Cloud Foundry Service](https://github.com/afforeroc/deploy-on-cloudfoundry).<br>
Additional, contains a web app sample for study and use.

## Tutorial
This tutorial was designed to be done on a personal computer. <br> 
Most every steps require using of console commands except when is indicated.

### 0. Required software
* Command prompt like Terminal, PowerShell, etc.
* Text editor like Notepad++, Visual Studio Code, etc.

### 1. Install Node JS and Express
1.1 Install stable/latest version of [Node.js](https://nodejs.org/en/).

1.2 Verify Node JS installation.
```
node --version
```
```
npm --version
```

1.3 Install and verify the framework.
```
npm install express-generator -g
```
```
express --version
```

> If you can't see the framework version on Windows, launch a PowerShell window as an administrator and enter this following command. Later, try again to verify.
```
Set-ExecutionPolicy Unrestricted
```

### 2. Create and run the app
2.1 Create the app.
```
express --view=pug express-app
```

2.2 Go to root folder `express-app` and install all necessary libraries.
> Do this step if you downloaded the web app sample.
```
cd express-app
```
```
npm install
```

2.3 Run the app locally. Later, open your favorite web browser on `localhost:3000`.
> Remember give access to Node.js to use the local network 
```
npm start
```

2.4 Stop the app with <kbd>ctrl</kbd> + <kbd>C</kbd>.


### 3. Configure the app to deploy
Go to root folder `express-app\`

3.1  Create `manifest.yml` file and edit it with following template. You should change `name` attribute and their value should be **unique** because it will used as part of an **URL** where your app will deployed. For example, you can put your initials and today's date.
> Text 
```
---
applications:
- name: express-app-<initials>-<date>
  memory: 64M
```

3.2 The web app is configurated. Now, you can go to repository [Deploy a web application on Cloud Foundry Service](https://github.com/afforeroc/deploy-on-cloudfoundry) to learn how to deploy on Cloud.

## Reference links
* [Cloudant Node.js Client](https://github.com/cloudant/nodejs-cloudant)

## Information links
* [Express page](https://expressjs.com/)
* [Express Generator page](https://expressjs.com/es/starter/generator.html)
* [Cloud Foundry Documentation](https://docs.cloudfoundry.org/) 
* [Deploying with App Manifests](https://docs.cloudfoundry.org/devguide/deploy-apps/manifest.html)