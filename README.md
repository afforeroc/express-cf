# Create and configure an Express app to deploy on Cloud Foundry
This is a tutorial about how to create and configure a simple web app to deploy on cloud using Cloud Foundry service.<br>

## Tutorial
This tutorial was designed to be done on a personal computer.

### Required software
* Command-line interpreter like [Terminal](https://www.howtogeek.com/140679/beginner-geek-how-to-start-using-the-linux-terminal/).
* Text editor like [Visual Studio Code](https://code.visualstudio.com/).

### 1. Install Node.js and Express
1.1 Install stable/latest version of [Node.js](https://nodejs.org/en/).

1.2 Verify Node.js installation.
```
node --version
```
```
npm --version
```

1.3 Install and verify the framework.
```
sudo npm install express-generator -g
```
```
express --version
```

1.4 If you can't see the framework version on Windows. Launch a PowerShell window as an administrator and enter this following command. Later, try again to verify.
```
Set-ExecutionPolicy Unrestricted
```

### 2. Create and run the app
2.1 Create the app.
```
express --view=pug express-app
```

2.2 Enter to `express-app\` folder.
```
cd express-app
```

2.3 Install the dependencies to run it. The same if you downloaded the web app sample.

```
npm install
```

2.4 Run the app locally and later, open your favorite web browser on `localhost:3000`. Remember give access to Node.js to use local network.
```
npm start
```

2.5 Stop the app with <kbd>ctrl</kbd> + <kbd>C</kbd>.


### 3. Configure the app to deploy
3.1 Enter to `express-app\` folder and create `manifest.yml` file and edit it with following template. It's necessary customize and use a **unique** value for `name` attribute, because this will used as part of an **URL** string where your app will deployed.
```
---
applications:
- name: express-app-<initials>-<date>
  memory: 64M
```

3.2 The web app is configurated. Now, you can learn how to [Deploy a web application on Cloud Foundry Service](https://github.com/afforeroc/deploy-on-cloudfoundry).

## Reference links
* [Cloudant Node.js Client](https://github.com/cloudant/nodejs-cloudant)

## Information links
* [Express page](https://expressjs.com/)
* [Express Generator page](https://expressjs.com/es/starter/generator.html)
* [Cloud Foundry Documentation](https://docs.cloudfoundry.org/) 
* [Deploying with App Manifests](https://docs.cloudfoundry.org/devguide/deploy-apps/manifest.html)