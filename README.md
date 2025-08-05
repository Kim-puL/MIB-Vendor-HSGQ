# 📡 HSGQ-MIB

MIB ini dirancang untuk perangkat **HSGQ-G02ID** dan mendukung pemantauan serta manajemen penuh untuk sistem GPON, ONU/ONT, dan layanan triple-play. Kompatibel dengan **Zabbix, LibreNMS, Nagios**, dan tools monitoring berbasis SNMP lainnya.

---

## ✨ Fitur Utama

### 🖥️ System Monitoring
- Temperatur sistem (`0.1°C`)
- Tegangan sistem (mV)
- Konsumsi daya

### 🔍 Optical Monitoring
- Tx/Rx Power (`0.1 dBm`)
- Transmit Bias Current (`μA`)
- Temperatur modul optik

### 👨‍💼 ONU/ONT Management
- Status registrasi ONU
- Remote reboot & factory reset
- Pemantauan parameter optik per ONU
- Manajemen versi software
- Serial number tracking

### ⚙️ QoS Triple-Play
- Profil VoIP, Video, dan Data
- Jaminan bandwidth minimum/maksimum
- Prioritas lalu lintas

### 🧩 Layanan Tambahan
- Pemantauan status VoIP
- Manajemen WiFi (SSID, channel)
- IGMP snooping untuk IPTV
- Konfigurasi VLAN

### 🔐 Keamanan
- Limitasi MAC address
- Status firewall
- Keamanan port (port security)

### 🔄 Firmware Management
- Versi firmware
- Status upgrade
- Manajemen firmware terpusat

### 🚨 Critical Event Traps
- Perubahan status port
- Registrasi/deregistrasi ONU
- Suhu melebihi ambang batas (threshold)

---

## 📦 Cara Penggunaan

1. **Download file MIB**  
   [`📥 HSGQ-COMPLETE-MIB.mib`](#)

2. **Contoh Implementasi SNMP**
   ```bash
   # 🔁 Reboot ONU tertentu
   snmpset -v2c -c private olt-ip .1.3.6.1.4.1.50224.3.1.1.8.1.4C5E0CC5EF56 i 2

   # 🌡️ Baca temperatur ONU
   snmpget -v2c -c public olt-ip .1.3.6.1.4.1.50224.4.1.1.4.1.4C5E0CC5EF56

   # 🚀 Set bandwidth ONU
   snmpset -v2c -c private olt-ip .1.3.6.1.4.1.50224.5.1.1.4.1.4C5E0CC5EF56 u 1000000
   ```

---

## 🧭 Struktur OID

```
.1.3.6.1.4.1.50224 (hsgq)
├── 1  - system         : System monitoring
├── 2  - traps          : Critical event notifications
├── 3  - onuMgmt        : ONU/ONT management
├── 4  - optical        : Optical parameters
├── 5  - qos            : Quality of Service
├── 6  - l2switching    : MAC address tables
├── 7  - vlan           : VLAN configuration
├── 8  - security       : Security features
├── 9  - igmp           : Multicast management
├── 10 - firmware       : Firmware management
├── 11 - voip           : VoIP service status
└── 12 - wifi           : WiFi management
```

---

## 🧩 Kompatibilitas

File MIB ini kompatibel dengan:
- [x] LibreNMS
- [x] Zabbix
- [x] Nagios
- [x] Semua tools berbasis SNMP v2c
