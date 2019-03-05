# Configurar una aplicación web de Express para desplegarla en Cloud Foundry

Este tutorial te indicará como configurar una aplicación web de `Express` para desplegarla en Cloud Foundry.

* Nota: Al descargar este repositorio, la aplicación tendrá los archivos de configuración para el despliegue, pero es necesario que realices el paso 4.

## Requisitos básicos
* Ventana de comandos como `Terminal` o `PowerShell`
* Editor de texto/código como `Notepad++` o `Visual Studio Code`

### 1. Instalar Node.js y Express
* Instala la última versión de [Node.js](https://nodejs.org/en/)
* Verifica la instalación de Node.js: `$ node --version`
* Verifica la instalación de NPM: `$ npm --version`
* Instala express-generator: `$ npm install express-generator -g`
* Verifica la instalación de Express: `$ express --version`

### 2. Crear y probar la aplicación web
* Crea la aplicación: `$ express --view=pug express-cf`
* Accede a la carpeta raíz de la aplicación: `$ cd express-cf`
* Instala las librerias necesarias: `$ npm install`
* Corre la aplicación: `$ npm start`
> Abre tu navegador web en `localhost:3000`
* Detén la aplicación: `(Ctrl + C)`

### 3. Configurar la aplicación para el despliegue
Desde la carpeta raíz del proyecto
* Crea el archivo `manifest.yml` y editalo con la siguiente información:
```
---
applications:
- name: express-cf-<initials>-<date>
  memory: 64M
```

### 4. Colocar un nombre a la aplicación
* Dentro del archivo `manifest.yml`, cambia el valor del atributo `- name` colocando un nombre **único**. Puedes usar la plantilla para colocar tus iniciales y la fecha de hoy.

## Links de referencia
* Cloudant Node.js Client: https://github.com/cloudant/nodejs-cloudant

## Links de interés
* Documentación de Express.js: https://expressjs.com/
* Documentacion de express-generator: https://expressjs.com/es/starter/generator.html
* Documentación de Cloud Foundry: https://docs.cloudfoundry.org/ 
* Documentación sobre manifest.yml: https://docs.cloudfoundry.org/devguide/deploy-apps/manifest.html