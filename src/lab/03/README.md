# 🧪 Laboratorio 03 - QEMU/KVM y virt-manager

## 🖥️ ¿Qué es QEMU?

**QEMU (Quick Emulator)** es un emulador y virtualizador de código abierto que permite ejecutar sistemas operativos y programas dentro de máquinas virtuales. Puede funcionar por sí solo como emulador o aprovechar la aceleración por hardware al combinarse con KVM.

## ⚙️ ¿Qué es KVM?

**KVM (Kernel-based Virtual Machine)** es un módulo del kernel de Linux que convierte al sistema en un hipervisor, permitiendo ejecutar múltiples máquinas virtuales de forma eficiente utilizando los recursos físicos del sistema anfitrión. KVM requiere que el procesador tenga soporte de virtualización (Intel VT-x o AMD-V).

---

## 🧰 ¿Qué es virt-manager?

**virt-manager (Virtual Machine Manager)** es una interfaz gráfica que facilita la creación, configuración y administración de máquinas virtuales que corren con QEMU/KVM.

Se recomienda especialmente en entornos de laboratorio o educativos, ya que reduce la complejidad de la gestión de entornos virtualizados.

---

## 🚀 Instalación de virt-manager y sus dependencias

Para instalar todas las herramientas necesarias en sistemas basados en Debian o Ubuntu:

```bash
$ sudo apt update
$ sudo apt upgrade
$ sudo apt install qemu-kvm libvirt-daemon-system libvirt-clients bridge-utils virt-manager
```

### Opcional: agregar el usuario actual a los grupos correspondientes

Esto permite ejecutar y administrar VMs sin necesidad de usar `sudo`.

```bash
$ sudo adduser $USER libvirt
$ sudo adduser $USER kvm
```

> 🔁 Es necesario cerrar sesión y volver a iniciarla para que los cambios surtan efecto.

---

### 🔍 Verificación del servicio

Para comprobar que el servicio de virtualización está activo:

```bash
$ sudo systemctl status libvirtd
```

El resultado debe mostrar el estado como **active (running)**.

---

<div align="center">
<sub>2025 - CUNOC - Redes de Computadoras 1</sub>
</div>