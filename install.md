# Instalación de Ubuntu Server 24.04.3 en VirtualBox
Este documento describe paso a paso la instalación de **Ubuntu Server 24.04.3**, utilizando capturas de pantalla del instalador oficial, incluyendo la selección de idioma, red, almacenamiento, creación de usuario, instalación y finalización.


---

## 1. Seleccionar idioma de instalación

El instalador de Ubuntu inicia mostrando un menú con múltiples idiomas.  
Selecciona **Español** y presiona **Enter**.

![Seleccionar idioma](ubuntu-24.04.3-image1.png)

---

## 2. Configurar el teclado

Elige la distribución **Spanish** para el teclado y confirma con **Hecho**.

![Configurar teclado](ubuntu-24.04.3-image2.png)

---

## 3. Seleccionar tipo de instalación

Se recomienda seleccionar **Ubuntu Server (minimized)** para una instalación ligera.

![Tipo de instalación](ubuntu-24.04.3-image3.png)

---

## 4. Configuración de red

Ubuntu detectará automáticamente tu interfaz de red.  
Si tienes DHCP, verás que obtiene IP sin intervención manual.

Pulsa **Hecho**.

![Configuración de red](ubuntu-24.04.3-image4.png)

---

## 5. Configuración de proxy

Si no usas proxy, deja el campo vacío.

![Proxy](ubuntu-24.04.3-image5.png)

---

## 6. Configuración del mirror (repositorio)

Puedes usar el mirror por defecto o uno local.

![Mirror](ubuntu-24.04.3-image6.png)

El instalador verificará el repositorio:

![Mirror test](ubuntu-24.04.3-image7.png)

---

## 7. Configuración del almacenamiento

Selecciona **Custom storage layout** para particionar manualmente.

![Almacenamiento personalizado](ubuntu-24.04.3-image8.png)

---

## 7.1 Crear partición /boot (1 GB)

Ingresa tamaño: **1G** → formato **ext4** → Montaje → **/boot** → Crear

![Partición boot creada](ubuntu-24.04.3-image11-boot.png)

---

## 7.2 Crear partición SWAP (2 GB)

Ingresa tamaño: **2G** → formato **swap** → Crear

![Crear swap](ubuntu-24.04.3-image12-swap.png)
![Swap creada](ubuntu-24.04.3-image13-swap.png)

---

## 7.3 Crear partición raíz **/** (10 GB)

Formato: **ext4** → Montaje → **/**

![Crear root](ubuntu-24.04.3-image14-root.png)
![Root creada](ubuntu-24.04.3-image15-root.png)

---

## 7.4 Crear partición `/var` (resto del disco)

Tamaño: **11.997 G** → Formato recomendado: **xfs** → Montaje **/var**

![Crear var](ubuntu-24.04.3-image16-var.png)
![Var creada](ubuntu-24.04.3-image17-var.png)

---

## 7.5 Resumen de particiones

Tu tabla final deberá verse así:

![Resumen de particiones](ubuntu-24.04.3-image18-resumen.png)

---

## 8. Crear usuario y nombre del servidor

Define:

- Nombre real  
- Nombre del servidor  
- Nombre de usuario  
- Contraseña  

![Confirmar acción destructiva](ubuntu-24.04.3-image20-config.png)

---

## 9. Reiniciar sistema

Selecciona:

**Reiniciar ahora**

Una vez reiniciado, ya puedes iniciar sesión con tu usuario.

---

# ✔ Instalación finalizada
Tu servidor Ubuntu 24.04.3 ya está listo para configurarse según tus necesidades.

