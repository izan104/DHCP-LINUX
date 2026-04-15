# DHCP-LINUX
# 🖧 AC1 - DHCP Linux (Ubuntu Server)

## 📌 Descripción
Esta práctica consiste en la instalación y configuración de un servidor DHCP en Ubuntu Server 22.04 LTS. Se implementan dos subredes independientes (lectores y trabajadores), y el servidor asigna direcciones IP automáticamente según la configuración definida.

---

# 📑 Índice
1. Introducción  
2. Configuración de la red  
3. Instalación y configuración del DHCP  
4. Verificación y pruebas  
5. Conclusiones  

---

# 1️⃣ Introducción

El objetivo de esta práctica es implementar un servidor DHCP capaz de gestionar dos subredes diferentes dentro de la red 192.168.11.0/24:

- 📚 Red de lectores: 100 hosts  
- 💼 Red de trabajadores: 16 hosts  

El servidor asignará direcciones IP automáticamente según la subred correspondiente.

---

## 🧮 Cálculo de subredes

### 📚 Red de lectores
- Red: 192.168.11.0/25  
- Máscara: 255.255.255.128  
- Rango: 192.168.11.1 – 192.168.11.126  
- Broadcast: 192.168.11.127  
- IP servidor: 192.168.11.1  

---

### 💼 Red de trabajadores
- Red: 192.168.11.128/27  
- Máscara: 255.255.255.224  
- Rango: 192.168.11.129 – 192.168.11.158  
- Broadcast: 192.168.11.159  
- IP servidor: 192.168.11.129  

---

# 2️⃣ Configuración de la red

Se parte de la red base 192.168.11.0/24 y se divide en dos subredes:

- Lectores → 192.168.11.0/25  
- Trabajadores → 192.168.11.128/27  

Las direcciones de red y broadcast no se pueden asignar a hosts.

---

# 3️⃣ Instalación y configuración del DHCP

## 📦 Instalación del servidor DHCP

```bash id="6p8z4q"
sudo apt update
sudo apt install isc-dhcp-server -y
