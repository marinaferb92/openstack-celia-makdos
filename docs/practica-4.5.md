# practica-iaw-4.5

# Terraform

Terraform es una infraestructura que nos permite de forma automatizada crear, modificar y eliminar infraestructuras.
En esta practica vamos a hacerlo gestionando el servicio de AWS.

Para empezar, instalaremos Terraform como se nos indica en la guía oficial [guia oficial de terraform](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli).
Tambien deberemos instalar la herramienta de AWS cli y configurar nuestras credenciales de acceso utilizando el comando 
`` aws configure``
![image](https://github.com/user-attachments/assets/2a912569-dd0b-435f-adb8-b70a0f4b9948)


Una vez hecho podremos empezar a **Iniciar el directorio de trabajo** para ello ejecutaremos utilizaremos ``terraform init `` 

Con `terraform fmt` formatean el archivo de configuración para que sea más legible y `terraform validate` validamos el archivo de configuración
![mhIX5wvw6Y](https://github.com/user-attachments/assets/07295e35-66a2-46d2-8d62-9298c8ac4409)

`terraform plan` nos permite ver los cambios que se aplicarán antes de ejecutarlos. 

![CMR2erKpt0](https://github.com/user-attachments/assets/f5253b0d-cdb5-4782-a53f-930439c83882)

Una vez que tenemos seguridad de que nuestro archivo es correcto ejecutaremos `terraform apply` o `terraform apply -auto-approve, el segundo crea los recursos sin tener que estar confirmando, y veremos como se comienza a desplegar la infraestructura.

![KF30wPCKKg](https://github.com/user-attachments/assets/fa46a5ea-fd5a-413e-9fff-a66fa103701c)

![sdXN6cEYfJ](https://github.com/user-attachments/assets/ac1115c7-1939-42bf-a639-3c53822336af)

![wcblmYPKRe](https://github.com/user-attachments/assets/f39f67a7-c664-4606-9a22-90b457f7be13)

Una vez terminado si entramos en AWS vemos que la infraestructura está creada, con sus grupos de seguridad y las IPs flotantes creadas y asociadas a cada instancia.

![UA4vYrRa5s](https://github.com/user-attachments/assets/f6592c1c-edab-4088-9c27-e79dbe92b1a7)

![AfUt282x2Y](https://github.com/user-attachments/assets/435e0b5a-e49e-4a97-b8e0-d0ceed937171)


![Hbk3zCLvlz](https://github.com/user-attachments/assets/34e0c9ff-9b24-46a1-91e1-9545e25cc0ee)

Ejecutando `terraform show` podremos ver los recursos que tenemos creados y su estado

![P2FLgMwBxF](https://github.com/user-attachments/assets/e107f0a7-50c2-4b2e-a966-d1f20579e14f)

y con `terraform destroy` podremos destruir la infraestructura completa sin necesidad de indicar nada más, al igual que con apply si indicamos *-auto-approve** se eliminará todo sin necesidad de confirmación 

![Ia1MKhkhTy](https://github.com/user-attachments/assets/992712c2-7eaa-42b2-a477-cb5728e8e041)

![qJX3WcCZAC](https://github.com/user-attachments/assets/1f1f2f58-3f47-4d36-bc3c-0a95a0925a25)

![mZ0zAwIQiA](https://github.com/user-attachments/assets/33490ccb-52c3-4455-9939-fd6af2c907bd)
