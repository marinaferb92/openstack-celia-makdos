# practica-iaw-3.1
# Implantación de Moodle en AWS mediante Ansible

## 1. Introducción
En esta práctica, el objetivo es automatizar una instalación de Moodle utilizando una arquitectura de dos niveles, backend y frontend, en Amazon Web Services con Ansible.


Para ello crearemos 2 maquinas como en la [actividad 1.8](https://github.com/marinaferb92/practica-iaw-1.8.git) 

tendremos que tener en cuentas las ips de cada maquina para definirlas dentro del inventario de Ansible
![image](https://github.com/user-attachments/assets/7f0b6377-b681-4831-ad89-05fbb89689c8)

En cada playboock deberemos definir en que maquina queremos que se ejecuten los cambios 
![image](https://github.com/user-attachments/assets/f198a39c-48ba-483f-88c1-71ee0386820d)


tambien tendremos que tener nuestro dominio definido con la ip publica del balanceador para definirla dentro del archivo de variables [variables.yml](moodle/vars/variables.yml)

![image](https://github.com/user-attachments/assets/e95afabb-ac0c-47b5-b4b8-1bcd06debc12)

Una vez hecho esto ejecutamos [main.yml](moodle/main.yml), donde tendremos puestos todos los playbooks en el orden de ejcución que queremos, con el comando `ansible-playbook + la ruta de nuestro inmventario + nuesto usuario + nuestra ruta a la clave vockey`, comenzaremos a ejecutar los playbooks.

![eH8SlbNu8Y](https://github.com/user-attachments/assets/793e42f9-e037-43dd-b156-7ff9f86ee49f)

Una vez terminado nos dará un resumen de los cambios que ha realizado
![image](https://github.com/user-attachments/assets/8e0cf537-b1cc-4191-ab3b-19c5b73b4cdd)


Una vez hecho esto podremos entrar en nuestro moodle y entrando en el administrador con las claves predefinidas en las variables, podremos comenzar a configurarlo.

![W1FXFB2acW](https://github.com/user-attachments/assets/94076bb0-377c-4338-854e-cb42540748f8)
![BexNRLdXgj](https://github.com/user-attachments/assets/6f2dc546-6fc7-4144-9747-239f646f1d42)
![image](https://github.com/user-attachments/assets/a18a5eca-06fd-47dd-af82-49eeb00a1678)