# 🧪 Laboratorio 05 - Tipos de red - Bridged, NAT, Host-only

En este archivo se hablará sobre cómo las máquinas virtuales se comunican con la red. Me enfocaré en tres modos principales de conexión de red para máquinas virtuales:
1. **Bridged**
2. **NAT (Network Address Translation)**
3. **Host-only (Isolated)**

---

## Introducción

Las máquinas virtuales pueden comunicarse entre sí, con el host físico y con otras máquinas físicas en la red. Para lograr esto, se utilizan dos componentes virtuales:

- **NICs virtuales** (Network Interface Card)
- **Switches virtuales** o puentes

Un **switch virtual** es un dispositivo lógico de capa 2 que transmite tramas entre nodos. Las NICs virtuales de las máquinas virtuales se conectan a los puertos virtuales del switch virtual, que a su vez está enlazado a la NIC física del host y, por lo tanto, a la red física.

El principio básico de la comunicación en red es el mismo tanto para dispositivos virtuales como físicos. Cada switch virtual crea un dominio de broadcast separado, y para conectar diferentes dominios se requiere un **router de capa 3**.

---

## Modos de conexión de red de máquinas virtuales

### 1. Conexión Bridged

En el modo de conexión puenteada, una máquina virtual se conecta directamente a la red física mediante la NIC física del host.

- El host actúa como puente entre la red física y las máquinas virtuales.
    
- Las máquinas virtuales obtienen direcciones IP desde un servidor DHCP en la red física.
    
- Desde la perspectiva de otros dispositivos en la red, las máquinas virtuales son como cualquier otro equipo conectado.
    
- Este modo permite que las IPs de las máquinas virtuales sean visibles y accesibles directamente.
    
- Es ideal para máquinas virtuales que deben ofrecer servicios en la red, como servidores de correo, archivos o web.

![BRIDGED](https://static1.makeuseofimages.com/wordpress/wp-content/uploads/2023/01/bridged.jpg?q=50&fit=crop&w=825&dpr=1.5)
    

### 2. Conexión NAT (Network Address Translation)

En este modo, las máquinas virtuales utilizan al host como dispositivo NAT.

- Un servidor DHCP virtual asigna direcciones IP privadas a las máquinas virtuales.
    
- Estas máquinas forman una red interna separada de la red física.
    
- El host actúa como intermediario entre la red virtual y la red física, traduciendo direcciones IP.
    
- El tráfico que sale de una VM parece originarse desde el host.
    
- Este modo es adecuado para máquinas virtuales que actúan como estaciones de trabajo cliente, como para navegar por Internet o revisar correos electrónicos.
    
![NAT](https://static1.makeuseofimages.com/wordpress/wp-content/uploads/2023/01/nat.jpg?q=50&fit=crop&w=825&dpr=1.5)

### 3. Conexión Host-only (Isolated)

En este modo, las máquinas virtuales pueden comunicarse entre sí y con el host, pero **no** con otros dispositivos fuera del host.

- Forma una red virtual privada y aislada.
    
- Ideal para entornos de pruebas cerrados, como experimentos de ciberseguridad o simulaciones de ataques, sin riesgo de afectar la red real.
    
- No hay acceso a la red física ni a Internet a menos que se configure explícitamente.

![ISOLATED](https://static1.makeuseofimages.com/wordpress/wp-content/uploads/2023/01/host-only-network.jpg?q=50&fit=crop&w=825&dpr=1.5)
---  

## Conclusión

Cada tipo de conexión de red tiene su propósito según el entorno y las necesidades del usuario:

- **Bridged**: para servicios accesibles desde la red externa.
    
- **NAT**: para clientes que necesitan acceso a Internet pero no ser accesibles desde afuera.
    
- **Host-only**: para entornos privados de prueba y simulación.
    
---  

<div align="center">
<sub>2025 - CUNOC - Redes de Computadoras 1</sub>
</div>