## Instalación de Docker en GNU/Linux **Ubuntu 24.04.3**
### 1. Actualizar el sistema e instalar dependencias necesarias
``` bash
sudo apt-get update
sudo apt-get install -y ca-certificates curl gnupg

```
### 2. Agragar la clave GPG oficial de docker 
Se crea un directorio para las claves y descarga la clave oficial de docker:
``` bash
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg

``` 
### 3. Agregar el repositorio de Docker a las fuentes de APT
Añade el repositorio oficial de Docker a las fuentes de APT:
``` bash
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

```

### 4. Instalar Docker Engine
Instala Docker Engine y los paquetes relacionados:
``` bash
sudo apt-get install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

```
### 5. Verificar la instalación
Para confirmar que Docker se instaló correctamente, ejecuta:
``` bash
sudo docker run hello-world

```
Nota: Este comando descarga una imagen de prueba y la ejecuta en un contenedor. Si ves un mensaje de bienvenida, la instalación fue exitosa.

### 6. Ejecutar docker en usuario sin privilegios
Para permitir que tu usuario ejecute comandos de Docker sin usar sudo, se tiene que añadir el usuario al grupo docker:
``` bash
sudo usermod -aG docker $USER

``` 
Despues se tiene que cerrar la sesión actual y ingresar nuevamente para validar los cambios puedan aplicarse.
