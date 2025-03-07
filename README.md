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




