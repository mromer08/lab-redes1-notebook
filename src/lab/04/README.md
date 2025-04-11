# 🧪 Laboratorio 04 - Creación y Configuración de una Máquina Virtual con Debian

Este documento explica los pasos necesarios para crear una máquina virtual utilizando Debian, destacando las diferencias entre las versiones **Live** y de **instalación completa**, así como recomendaciones para descargar las imágenes ISO adecuadas y configurar el sistema una vez instalado.

---

## 🧠 Antes de Empezar: Live vs Instalación Completa

### 🔹 Modo Live (Live ISO)
- Arranca directamente desde el medio (USB o ISO).
- **No instala nada en el disco duro** por defecto.
- Ideal para equipos que no pueden modificar su sistema actual.
- **Recomendado** usar **persistencia** si se desea conservar archivos y configuraciones entre reinicios.
- Perfecto para pruebas o entornos de recuperación.

### 🔸 Instalación Completa (DVD ISO)
- Requiere instalar el sistema operativo en disco.
- Permite mayor personalización, instalación de servicios y entornos.
- Recomendado para servidores o laboratorios de trabajo persistente.

---

## 📥 Descarga de Imágenes ISO

### ✅ Sitio oficial: [Debian](https://www.debian.org)

### 🔹 Recomendaciones de descarga:

#### 1. **ISO Live Modo Terminal (sin entorno gráfico)**
- Ir a la sección de [otras descargas de Debian Live](https://cdimage.debian.org/debian-cd/current-live/amd64/iso-hybrid/).
- Seleccionar la versión `standard.iso` (~1.4 GB).
- Ideal para USBs con persistencia o pruebas desde máquina virtual.

#### 2. **ISO de Instalación Completa (DVD)**
- Descargar desde [otras descargas](https://www.debian.org/distrib/)
- Recomendado: `debian-XX.X.X-amd64-DVD-1.iso` (≈ 3.7 GB).
- Permite instalaciones en terminal o con entorno gráfico.

---

## 🛠️ Creación de la Máquina Virtual con Virt-Manager

1. **Abrir Virt-Manager** y seleccionar "Crear nueva máquina virtual".
2. Seleccionar la ISO descargada.
3. Elegir:
   - Sistema Operativo: Debian 12, si no lo detecta automaticamente se pueden buscar versiones anteriores de Debian en el menu.
   - RAM recomendada: 1-2 GB.
   - CPU: 1 (o más si es necesario).
4. Crear disco virtual (recomendado: 5-8 GB).
5. Red: tipo **NAT** (permite conectividad sin configuración adicional).
6. Finalizar y arrancar la máquina.

---

## ⚙️ Instalación y Configuración (Versión DVD)

1. Iniciar con la opción `Graphical Install`.
2. Seguir el asistente de instalación
3. Configurar conexión a internet:
   - Activar uso de **network mirror** para que funcione `apt` luego.
   - Elegir país y mirror (por defecto).
4. Selección de software:
   - **Desactivar entornos gráficos** si no se desean.
   - Activar únicamente "utilidades estándar del sistema" y "servidor SSH".
5. Instalar GRUB en el disco principal.
6. Reiniciar al finalizar.

---

## 💡 Tips Adicionales

- Si **no configuras el mirror de red**, `apt` no funcionará hasta que lo ajustes manualmente editando `/etc/apt/sources.list`.
- El usuario creado durante la instalación no es root, pero puede obtener privilegios con `sudo`.
- En modo Live, el usuario por defecto es `user`, contraseña: `live`.

### Archivo `sources.list`
Por defecto solo viene la primera linea. Comentarla y copiar lo demas para configurar apt

```bash
#deb cdrom:[Debian GNU/Linux 12.6.0 _Bookworm_ - Official amd64 NETINST with firmware 20240629-10:18]/ bookworm contrib main non-free-firmware

deb http://deb.debian.org/debian/ bookworm main non-free-firmware
deb-src http://deb.debian.org/debian/ bookworm main non-free-firmware

deb http://security.debian.org/debian-security bookworm-security main non-free-firmware
deb-src http://security.debian.org/debian-security bookworm-security main non-free-firmware

deb http://deb.debian.org/debian/ bookworm-updates main non-free-firmware
deb-src http://deb.debian.org/debian/ bookworm-updates main non-free-firmware

```

---

## ✅ Verificación

Una vez instalada la VM:

```bash
# Iniciar sesión como el usuario creado
login: estudiante
password: *****

# Verificar conexión a internet
ping 8.8.8.8

# Actualizar paquetes
sudo apt update && sudo apt upgrade
```

---

<div align="center">
<sub>2025 - CUNOC - Redes de Computadoras 1</sub>
</div>