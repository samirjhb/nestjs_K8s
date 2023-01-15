
## Descripcion

Este proyecto tiene como finalidad el proceso de integrar herramienta tales como NestJS, Docker y Kubernetes


Para subir una API desarrollada con NestJS a Kubernetes, necesitará seguir los siguientes pasos:

1. Crear un archivo de configuración de Kubernetes (llamado "Manifest") que describa los recursos necesarios para su aplicación, como contenedores, volúmenes y servicios.

2. Construir una imagen de Docker de su aplicación. Esto puede hacerse automáticamente mediante un archivo "Dockerfile" o utilizando una plataforma de construcción de contenedores como Jenkins o Travis CI.

3. Publicar la imagen de Docker en un registro de contenedores, como Docker Hub o Google Container Registry.

4. Crear una instancia de Kubernetes en su plataforma de elección (como Google Kubernetes Engine o Amazon Elastic Kubernetes Service).

5. Usar el comando "kubectl" para aplicar el archivo de configuración de Kubernetes y desplegar su aplicación en el cluster.

6. Configurar los servicios y las rutas de acceso para que su aplicación sea accesible desde internet.

Es recomendable que tenga conocimientos previos en Kubernetes y Docker para realizar este proceso. También es recomendable tener un entorno de desarrollo configurado correctamente con las herramientas necesarias para poder construir la imagen de Docker y aplicar el archivo de configuración de Kubernetes.

## Intalacion 

```bash
$ npm install
```

## Running the app

```bash
# development
$ npm run start

# watch mode
$ npm run start:dev

# production mode
$ npm run start:prod
```

## Test

```bash
# unit tests
$ npm run test

# e2e tests
$ npm run test:e2e

# test coverage
$ npm run test:cov
```

## Paso a Paso

```bash

#Subir DockerFile a DockerHub
$ docker build -t samirjhb/nestjs-k8s .

$ docker push samirjhb/nestjs-k8s

# Irse a la carpeta de K8S para crear el deploymet
$ kubectl create -f deployment.yaml

# Verificar el PODS
$ kubectl get pods -o wide

#Seleccionar el POD a revisar 
$ kubectl logs nestjs-k8s-786566ccf7-c2dl7

# Posteriomente  creacion del servicio 
$ kubectl create -f service.yaml

#Verificacion del service 
$ kubectl get service


```




## Autor 

-  🧑🏻‍💻 Samir Hadechni - [Portafolio](https://samirjhb.github.io/PortaFolio.github.io/)


