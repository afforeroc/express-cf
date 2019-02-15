# Crear y desplegar una aplicación web de Express.js en Cloud Foundry de IBM Cloud

> Presentación [Introducción a Cloud Foundry](https://ibm.box.com/v/cf-ppt)

Este tutorial te indicará como crear y desplegar una aplicación web de Express.js en Cloud Foundry de IBM Cloud usando SHELL. Una vez la aplicación este desplegada será accesible desde cualquier navegador. 

Después de teminar este pattern usted entenderá como:
* Crear una aplicación web de Express.js desde cero
* Usar el CLI de IBM Cloud
* Desplegar aplicaciones web por medio del manifest.yml y el package.json

## Servicios Incluidos
* [IBM Cloud - Cloud Foundry](https://www.ibm.com/cloud/cloud-foundry): Servicio en la nube que ejecuta código en una plataforma como servicio (PaaS), open source, serverless y altamente escalable.

## Prerequisitos
* Cuenta activa de [IBM Cloud](https://console.bluemix.net)
* Manejo básico de la ventana de comandos tipo CMD, PowerShell o Terminal.
* Tener instalado ```Node.js v10.15.1``` o superior.

### 0. Instalar IBM Cloud CLI
* Instala en Mac/Linux: ```$ curl -sL https://ibm.biz/idt-installer | bash```
* Instala en Windows: https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64
* Verifica la versión del CLI: ```$ ibmcloud -v```

### 1. Opción A: Crea la aplicación desde cero
* Instala el generador de express: ```$ npm install express-generator -g```
* Genera la aplicación: ```$ express --view=pug express-cf```
* Posiciónate dentro de la carpeta raíz del repositorio: ```$ cd express-cf```
* Crea y guarda el archivo ```.gitignore``` con la información de este repositorio
* Crea y guarda el archivo ```manifest.yml``` con la información de este repositorio

### 1. Opción B: Clonar el repositorio
* Clona este repositorio localmente:  ```$ git clone https://github.com/afforeroc/express-cf```
* Posiciónate dentro de la carpeta raíz del repositorio: ```$ cd express-cf```

### 2. Probar la aplicación web de forma local
* Instala las librerias necesarias: ```$ npm install```
* Corre la aplicación: ```npm start```
* Abre el navegador web en: http://localhost:3000/

### 3. Login con IBM Cloud CLI 
*	Inicia sesión en IBM Cloud: ```$ ibmcloud login``` 
* Configura la organización y espacio de Cloud Foundry: ```$ ibmcloud target -cf```
* Si deseas cambiar de organización y/o espacio: ```$ ibmcloud target -o <organization name> -s <spacename>```

### 4. Desplegar la aplicación usando el CLI
* En el archivo `manifest.yml`, cambia el valor del atributo `- name` colocando un nombre **único**, ya que este será usado como parte del subdominio generado. Puedes usar la plantilla del repositorio para colocar tus iniciales y la fecha del día de hoy.
```
---
applications:
- name: express-cf-<initials>-<date>
  memory: 64M
```
* En el archivo `package.json`, verifica que exista la linea/comando `"start": ...` dentro de la sección `"scripts"`, ya que este permitirá ejecutar la aplicación en la nube.
```
"scripts": {
    "start": "node ./bin/www"
  },
```
* Sube la aplicación a IBM Cloud: ```$ ibmcloud app push ```
*	Visualiza tu aplicación web accediendo al [dashboard de IBM Cloud](https://console.bluemix.net/dashboard/apps)

## Links de interés:
* Documentación de Express.js: https://expressjs.com/
* Documentacion de express-generator: https://expressjs.com/es/starter/generator.html
*	Documentación de IBM Cloud: https://console.bluemix.net/docs/
*	Documentación de Cloud Foundry: https://docs.cloudfoundry.org/ 
* Documentación sobre manifest.yml: https://docs.cloudfoundry.org/devguide/deploy-apps/manifest.html