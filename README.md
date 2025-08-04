Fitur Utama MIB:

System Monitoring:
Temperatur sistem (0.1°C)
Voltage sistem (mV)
Status redundansi
Optical Monitoring:
Tx/Rx Power (0.1 dBm)
Transmit Bias Current (μA)
Modul temperatur (0.1°C)

ONU/ONT Management:
Rx Power di OLT (dari ONU)
Tx Power dari ONU
Rx Power di ONU
Voltage ONU (mV)
Jarak ONU (meter)
Status ONU (registrasi, operasional)

QoS Triple-Play:
Profil VoIP, Video, Data
Garansi bandwidth
Prioritas traffic
Mapping ke ONU spesifik

Critical Event Traps:
Perubahan status port
Suhu melebihi threshold
Failover OLT

Cara Penggunaan:
Simpan file sebagai HSGQ-OLT-MIB.mib
Gunakan dengan SNMP manager (Zabbix, Nagios, LibreNMS)

Contoh OID:
Temperatur: .1.3.6.1.4.1.50224.1.1
Voltage: .1.3.6.1.4.1.50224.1.3
ONU Tx Power: .1.3.6.1.4.1.50224.4.1.1.6

Contoh SNMP Get:
bash
# Get system temperature (0.1°C)
snmpget -v2c -c public olt-ip .1.3.6.1.4.1.50224.1.1.0

# Get ONU Tx Power (0.1 dBm)
snmpget -v2c -c public olt-ip .1.3.6.1.4.1.50224.4.1.1.6.1.4C5E0CC5EF56

# Get optical Rx power on port 1
snmpget -v2c -c public olt-ip .1.3.6.1.4.1.50224.5.1.1.2.1
File MIB ini siap diimplementasikan pada perangkat HSGQ OLT dan kompatibel dengan semua sistem manajemen jaringan standar.
