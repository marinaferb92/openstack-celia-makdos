# openstack-celia-makdos
#Creación de un sitio web estático con MkDocs y GitHub Pages
En esta práctica llevaremos a cabo la creación y configuración de un sitios web estático **MkDocs** y lo publicaremos en **GitHub Pages**


## Pasos Previos
Tendremos una maquina en AWS con docker instalado para el despliegue de la aplicación

## 1. Instalación y configuración
Una vez dentro de nuestra máquina ejecutamos el siguiente comando para ejecutar un nuevo proyecto 
``
docker run --rm -it -p 8000:8000 -u $(id -u):$(id -g) -v "$PWD":/docs squidfunk/mkdocs-material new .
``

![image](https://github.com/user-attachments/assets/ae4e89e0-8415-4b3f-900a-c58a0d0c7c3f)

Este comando creará la diguiente estructura 
``
proyecto/
│── docs/
│   └── index.md
└── mkdocs.yml
``

## 2. Configuración en mkdocs.yml
Una vez creado el archivo `mkdocs.yml` podremos editarlo para ir configurando nuestro sitio web
````
site_name: Marina mkdocks 

nav:
    - Principal: index.md                    
    - Practica 3.1: practica-3.1.md
    - Practica 4.5: practica-4.5.md
````
1. Nombre del sitioweb y menú de navegación.
   
![image](https://github.com/user-attachments/assets/6d17879e-7193-459b-b6ef-0269fb1e7b36)

````
theme:
  name: material                       #theme material 

  palette:
    # Modo claro
    - scheme: default
      primary: teal                      
      accent: black
      toggle:
        icon: material/toggle-switch
        name: Switch to dark mode

    # Modo oscuro
    - scheme: slate
      primary: teal
      accent: black
      toggle:
        icon: material/toggle-switch-off-outline
        name: Switch to light mode
````
2. Definimos que  el color principal del tema sea teal(verde azulado), color de acento negro y además creamos la opción de que mediante un botón podamos poner la página en modo claro o oscuro.
![MChg4yDb8U](https://github.com/user-attachments/assets/c4f9c39d-3640-499d-9d76-e737b09bf7f8)
![image](https://github.com/user-attachments/assets/f40245c7-3d4b-4180-aeb5-9a09fbf9cebc)

````
  features:
    - header.autohide
    - navigation.footer
````
3. Establecemos la opcion de que la barra superior se oculte al scrolear hacia abajo y que se muestren botones de navegación en el pié de página.
![image](https://github.com/user-attachments/assets/6191ad77-6fb1-4af5-ad40-43cb8d5b7f0f)

````
extra:
  language: es
  social:
    - icon: fontawesome/brands/github 
      link: https://github.com/marinaferb92
    - icon: fontawesome/brands/docker
      link: https://hub.docker.com/u/marinaferb92

plugins:
  - offline

copyright: Copyright - 2025 Marina Fernandez
````
4. Establecemos el idioma del sitio en Español, y agregamos dos iconos en el footer que nos llevarán a la nuestra página de *GitHub* y a *Docker Hub*.
5. Ademas añadimos el plugging con que el que podremos navegar por la documentacion sin conexión y un mensaje de Copyright en el pie de página.

![bielOdmItG](https://github.com/user-attachments/assets/3d7f30e6-95f1-4dd5-9d34-b11c0cc82eb3)

## 2. Ejecutar el servidor local
Para previsualizar como quedaría el sitio web, podemos ejecutar el siguiente comando 
```
docker run --rm -it -p 8000:8000 -u $(id -u):$(id -g) -v "$PWD":/docs squidfunk/mkdocs-material
```
Y para visualizarlos abriremos un navegador e introduciremos la siguiente dirección ``http://localhost:8000``

![D5exN9trWA](https://github.com/user-attachments/assets/fd59bbb5-09dc-4b3d-8d7e-9fca5019bc65)

## 3. Generar la documentación
Para general los archivos HTML estáticos ejecutamos 
``
docker run --rm -it -u $(id -u):$(id -g) -v "$PWD":/docs squidfunk/mkdocs-material build
``
![SiIgvDrcsI](https://github.com/user-attachments/assets/b53839b0-5ed8-4b6d-b1f5-e9f65736aa7e)

## 4. Publicar en GitHub Pages
Entraremos en nuestra página de *GitHub* y creamos la rama y hacemos un push de los repositorios
![image](https://github.com/user-attachments/assets/8ea6ec2a-ad00-478b-af39-12ef3279b44c)

## 4. Publicar en GitHub Pages
Automatizaremos la publicación del sitio Web con *GitHub Actions*
para ellos entramos en **Actions** y creamos un nuevo *Workflow* al que llamaremos [build-push-mkdocs.yaml](.github/workflows/build-push-mkdocs.yaml)

A continuación en *Settings* -> *Actions* -> *General*
Le damos a *Workflow permissions* **Read and write permissions**.

![image](https://github.com/user-attachments/assets/f111dea7-c511-4749-a254-2d904012bb7d)

Una vez todo configurado deberia salir un :heavy_check_mark: que indica que el script de automatizacion se ejecuta correctamente.

Ahora si quisieramos entrar en nuestro sitio web deberemos introducir en el navegador la direccion de la siguiente forma
``
https://<usuarios-github>.github.io/<Nombre del repositorio>/``

![image](https://github.com/user-attachments/assets/964e83f2-2949-473a-b73d-9f18482e871c)


## 4. Creación de secciones
Una vez todo configurado podremos ir añadiendo secciones y escribiendo en estas en formato *Markdown*.

Si queremos añadir fotos deberemos crear una carpeta a la que llamaremos *images* donde depositaremos las fotos que queremos subir a nuestra web, luego haremos referencia a ellas de la siguiente manera para que puedan visualizarse

![image](https://github.com/user-attachments/assets/41e0c963-edd0-452b-99a9-90a7af801d44)

![image](https://github.com/user-attachments/assets/81546fb7-f011-4925-b951-f15d1aa1a410)




