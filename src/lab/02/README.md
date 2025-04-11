# 🧪 Laboratorio 02 - Wireshark y Análisis de Paquetes

## 🔍 ¿Qué es [Wireshark](https://www.wireshark.org/)?

Wireshark es un analizador de protocolos de red gratuito y de código abierto. Permite examinar el tráfico de red en tiempo real o desde archivos previamente capturados. Con esta herramienta, se pueden estudiar los detalles de los paquetes transmitidos en una red, lo que resulta útil para fines educativos, diagnósticos y de seguridad.

---

## 🛠️ Otras Herramientas de Captura de Paquetes

- **Tcpdump** – Herramienta de línea de comandos para captura de paquetes.
- **Snort** – Sistema de detección de intrusos con capacidades de análisis.
- **Capsa** – Analizador gráfico para ambientes Windows.
- **SolarWinds** – Suite comercial con herramientas para monitoreo de red.

---

## 📦 ¿Qué es un paquete?

Un **paquete** es una unidad estructurada de datos transmitida a través de una red. Cada paquete contiene información de encabezado y de carga útil, permitiendo una comunicación ordenada, segmentada y confiable entre dispositivos.

> ⚠️ Para sacar el máximo provecho de Wireshark, es fundamental comprender el modelo OSI.

---

## 🧱 Modelo OSI

| Capa                | Descripción                                                                 |
|---------------------|------------------------------------------------------------------------------|
| Física              | Señales eléctricas, medios de transmisión y bits                             |
| Enlace de Datos     | Tramas, direcciones MAC, control de acceso al medio                         |
| Red                 | Direccionamiento IP, enrutamiento, paquetes                                 |
| Transporte          | Segmentación, control de flujo, puertos (TCP/UDP)                           |
| Sesión              | Establecimiento, mantenimiento y terminación de sesiones                    |
| Presentación        | Codificación, cifrado, compresión                                            |
| Aplicación          | Protocolos de usuario como HTTP, FTP, DNS, SMTP                             |

---

## 🖥️ Partes Básicas de Wireshark

- **Barra de Filtro**  
  Permite escribir filtros para visualizar solo los paquetes relevantes.  
  ![Barra de filtro](https://www.wireshark.org/docs/wsug_html_chunked/images/ws-filter-toolbar.png)

- **Panel de Listado de Paquetes**  
  Muestra todos los paquetes capturados durante una sesión.  
  ![Listado de paquetes](https://www.wireshark.org/docs/wsug_html_chunked/images/ws-list-pane.png)

- **Panel de Detalle de Paquetes**  
  Muestra la información estructurada del paquete seleccionado.  
  ![Detalle de paquete](https://www.wireshark.org/docs/wsug_html_chunked/images/ws-details-pane.png)

- **Panel de Bytes de Paquetes**  
  Muestra la información cruda del paquete seleccionado en formato hexadecimal (hexdump).  
  ![Bytes del paquete](https://www.wireshark.org/docs/wsug_html_chunked/images/ws-bytes-pane.png)

---

## 🧠 Conceptos de Interés

- ¿Qué es el modo promiscuo?  
- ¿Es legal monitorear una red pública?  
- ¿Qué impacto tiene el cifrado en el análisis de paquetes?  
- ¿Es posible reconstruir archivos o mensajes a partir de paquetes capturados?  

---

<div align="center">
<sub>2025 - CUNOC - Redes de Computadoras 1</sub>
</div>