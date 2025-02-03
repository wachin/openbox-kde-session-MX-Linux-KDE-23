# **Cómo instalar y configurar tint2 con Openbox en MX Linux 23 KDE**

Este tutorial está diseñado para usuarios de **MX Linux 23 KDE** que desean instalar y configurar el panel **tint2** para usarlo junto con el gestor de ventanas **Openbox**.

---

## **1. Descarga e instalación de MX Linux 23 KDE**

Si aún no tienes **MX Linux 23 KDE**, puedes descargarlo desde los siguientes enlaces oficiales:

- [Página oficial de MX Linux](https://mxlinux.org/download-links/)
- [SourceForge - MX Linux KDE](https://sourceforge.net/projects/mx-linux/files/Final/KDE/)

Instálalo en tu sistema siguiendo las instrucciones estándar de instalación de MX Linux.

---

## **2. Instalar Openbox y herramientas necesarias**

1. Abre una terminal y ejecuta el siguiente comando para instalar **Openbox** y las herramientas adicionales necesarias:
   ```bash
   sudo apt install git obkey tint2 picom xfce4-notifyd obmenu2 gnome-icon-theme \
       numlockx lxrandr nitrogen volumeicon-alsa obconf lxsession-logout
   ```

   - `git`: Permite clonar y gestionar repositorios de código fuente.
   - `obkey`: Herramienta gráfica para configurar atajos de teclado en Openbox.
   - `tint2`: Un panel ligero y personalizable para Openbox.
   - `picom`: Compositor de ventanas que agrega efectos visuales como transparencias y sombras.
   - `xfce4-notifyd`: Servicio de notificaciones de escritorio basado en XFCE, compatible con Openbox, este es absolutamente necesario ejemplo para emparejar el [teclado Logitech Pebble Keys 2 K380s](https://facilitarelsoftwarelibre.blogspot.com/2025/01/como-emparejar-el-teclado-logitech-pebble-keys-2-k380s-en-mx-linux-23-kde.html).
   - `obmenu2`: Editor de menús para Openbox que permite personalizar la estructura del menú.
   - `gnome-icon-theme`: Paquete de íconos para mejorar la apariencia visual del entorno.
   - `numlockx`: Activa el bloqueo numérico en el inicio de sesión.
   - `lxrandr`: Herramienta para gestionar la resolución de pantalla y configuraciones de monitores.
   - `nitrogen`: Aplicación ligera para establecer fondos de pantalla.
   - `volumeicon-alsa`: Indicador de volumen de sonido basado en ALSA, con clic derecho se abrirá pavucontrol el cual debe estar instalado por defecto y en caso que no instalarlo.
   - `obconf`: Herramienta para configurar Openbox mediante una interfaz gráfica.
   - `lxsession-logout`: Utilidad para cerrar sesión, apagar o reiniciar el sistema desde Openbox, debe añadirla al panel tint2, abajo dejo un enlace a un tutorial.

2. Descarga y configura los archivos de Openbox ejecutando:
   ```bash
   git clone https://github.com/wachin/openbox-kde-session-MX-Linux-KDE-23/ ~/.config/openbox
   ```

3. Cierra la sesión o reinicia tu computadora.

4. En la pantalla de inicio de sesión, selecciona **Openbox** como tu entorno de escritorio y accede con tu usuario.

---

## **3. Configuración inicial de Openbox**

### **3.1. Configurar atajos de teclado con obkey**

- Para personalizar los atajos de teclado en Openbox, abre una terminal y ejecuta:
  ```bash
  obkey
  ```
- Esto abrirá una ventana donde puedes:
  - Agregar nuevos atajos.
  - Modificar los existentes.
  - Eliminar los que no necesites.

Guarda los cambios al terminar y ciérralo.

---

## **4. Configuración de programas al inicio**

El archivo `~/.config/openbox/autostart` controla los programas que se ejecutan al iniciar Openbox. A continuación se explica la función de cada uno:

- `nitrogen --restore &` → Restaura el fondo de pantalla previamente configurado con Nitrogen.
- `picom --experimental-backends &` → Activa el compositor de ventanas para mejorar los efectos visuales como transparencia y sombras.
- `tint2 &` → Inicia el panel tint2, que proporciona una barra de tareas y un área de notificaciones.
- `volumeicon &` → Inicia el icono de volumen para controlar el audio del sistema.
- `numlockx on &` → Activa el bloqueo numérico al iniciar sesión.
- `xfce4-notifyd &` → Habilita las notificaciones del sistema.
- `lxrandr --auto &` → Configura automáticamente la resolución de pantalla.

Si deseas modificar los programas que se inician con Openbox, edita el archivo `autostart` y agrega o elimina procesos según tus necesidades.

---

## **5. Configurar un fondo de pantalla con Nitrogen**

1. Abre **Nitrogen** desde el menú de aplicaciones.
2. Haz clic en **Preferences** y luego en **+ Add**.
3. En la ventana emergente, navega hasta el directorio:
   ```
   /usr/share/wallpapers/
   ```
4. Selecciona la carpeta y haz clic en **Seleccionar** y luego en **OK**.
5. Elige un fondo de pantalla de la lista que aparece.
6. Da clic a la izquierda en "Automatic" y selecciona "Scaled" para que la imagen ocupe toda la pantalla.
7. Haz clic en **Apply** para aplicarlo y luego cierra Nitrogen.

---

## **6. Recursos adicionales**

Para más configuraciones avanzadas de Openbox, puedes consultar los siguientes recursos:

- **Guía de configuración oficial de Openbox**:  
  [https://openbox.org/help/Configuration](https://openbox.org/help/Configuration#:~:text=From%20Openbox&text=Default%20configuration%20file%20can%20by,config%2Fopenbox%2F.)

- **Wiki de Openbox en Arch Linux**:  
  [https://wiki.archlinux.org/title/Openbox](https://wiki.archlinux.org/title/Openbox)

---

## **7. Consideraciones finales**

- Si necesitas configurar tint2 (el panel), sigue los pasos del:

**Cómo instalar y configurar tint2 con Openbox en MX Linux 23 KDE**  
[https://github.com/wachin/Facilitar-el-Software-Libre/blob/main/Tutoriales/tint2/C%C3%B3mo%20instalar%20el%20panel%20tint2%20para%20usarlo%20con%20openbox/Instalar%20tint2%20para%20openbox.md](https://github.com/wachin/Facilitar-el-Software-Libre/blob/main/Tutoriales/tint2/C%C3%B3mo%20instalar%20el%20panel%20tint2%20para%20usarlo%20con%20openbox/Instalar%20tint2%20para%20openbox.md).

- Explora las configuraciones de Openbox para personalizar completamente tu entorno de escritorio.

---

Dios te bendiga

