# Runbook --- EdgeSwitch 24 (16 Jaulas · 4 Cámaras)

> Checklist operativo. Copiar y pegar.

------------------------------------------------------------------------

## □ PC

``` text
IP:      192.168.1.100
Máscara: 255.255.255.0
```

------------------------------------------------------------------------

## □ Entrar

``` bash
ssh-keygen -R 192.168.1.2

ssh -o KexAlgorithms=+diffie-hellman-group1-sha1 -o HostKeyAlgorithms=+ssh-rsa -o MACs=+hmac-sha1 ubnt@192.168.1.2
```

Usuario: **ubnt**\
Contraseña: **ubnt**

------------------------------------------------------------------------

## □ Cambiar nombre e IP

### Switch 1 (`SW-J101-J102`)

``` text
enable
configure
snmp-server sysname SW-J101-J102
exit
network protocol none
network parms 192.168.1.2 255.255.255.0 192.168.1.1
```

### Switch 2 (`SW-J103-J104`)

``` text
enable
configure
snmp-server sysname SW-J103-J104
exit
network protocol none
network parms 192.168.1.3 255.255.255.0 192.168.1.1
```

### Switch 3 (`SW-J105-J106`)

``` text
enable
configure
snmp-server sysname SW-J105-J106
exit
network protocol none
network parms 192.168.1.4 255.255.255.0 192.168.1.1
```

### Switch 4 (`SW-J107-J108`)

``` text
enable
configure
snmp-server sysname SW-J107-J108
exit
network protocol none
network parms 192.168.1.5 255.255.255.0 192.168.1.1
```

### Switch 5 (`SW-J109-J110`)

``` text
enable
configure
snmp-server sysname SW-J109-J110
exit
network protocol none
network parms 192.168.1.6 255.255.255.0 192.168.1.1
```

### Switch 6 (`SW-J111-J112`)

``` text
enable
configure
snmp-server sysname SW-J111-J112
exit
network protocol none
network parms 192.168.1.7 255.255.255.0 192.168.1.1
```

### Switch 7 (`SW-J113-J114`)

``` text
enable
configure
snmp-server sysname SW-J113-J114
exit
network protocol none
network parms 192.168.1.8 255.255.255.0 192.168.1.1
```

### Switch 8 (`SW-J115-J116`)

``` text
enable
configure
snmp-server sysname SW-J115-J116
exit
network protocol none
network parms 192.168.1.9 255.255.255.0 192.168.1.1
```

------------------------------------------------------------------------

## □ Reconectar

``` bash
ssh -o KexAlgorithms=+diffie-hellman-group1-sha1 -o HostKeyAlgorithms=+ssh-rsa -o MACs=+hmac-sha1 ubnt@[IP_DEL_SWITCH]
```

``` text
enable
write memory
```

------------------------------------------------------------------------

## □ Crear VLAN

``` text
enable
vlan database
vlan 11,12,13,14,21,22,23,24,31,32,33,34,41,42,43,44,51,52,53,54,61,62,63,64,71,72,73,74,81,82,83,84,91,92,93,94,101,102,103,104,111,112,113,114,121,122,123,124,131,132,133,134,141,142,143,144,151,152,153,154,161,162,163,164,200
exit
```

------------------------------------------------------------------------

## □ Configurar puertos de cámara

Abrir el archivo correspondiente (`01-SW...md` a `08-SW...md`) y copiar
el bloque completo.

------------------------------------------------------------------------

## □ Configurar enlaces

``` text
configure

interface 0/25
vlan participation include 11,12,13,14,21,22,23,24,31,32,33,34,41,42,43,44,51,52,53,54,61,62,63,64,71,72,73,74,81,82,83,84,91,92,93,94,101,102,103,104,111,112,113,114,121,122,123,124,131,132,133,134,141,142,143,144,151,152,153,154,161,162,163,164,200
vlan tagging 11,12,13,14,21,22,23,24,31,32,33,34,41,42,43,44,51,52,53,54,61,62,63,64,71,72,73,74,81,82,83,84,91,92,93,94,101,102,103,104,111,112,113,114,121,122,123,124,131,132,133,134,141,142,143,144,151,152,153,154,161,162,163,164,200
vlan acceptframe all
exit

interface 0/26
vlan participation include 11,12,13,14,21,22,23,24,31,32,33,34,41,42,43,44,51,52,53,54,61,62,63,64,71,72,73,74,81,82,83,84,91,92,93,94,101,102,103,104,111,112,113,114,121,122,123,124,131,132,133,134,141,142,143,144,151,152,153,154,161,162,163,164,200
vlan tagging 11,12,13,14,21,22,23,24,31,32,33,34,41,42,43,44,51,52,53,54,61,62,63,64,71,72,73,74,81,82,83,84,91,92,93,94,101,102,103,104,111,112,113,114,121,122,123,124,131,132,133,134,141,142,143,144,151,152,153,154,161,162,163,164,200
vlan acceptframe all
exit
```

------------------------------------------------------------------------

## □ Finalizar

``` text
write memory

show running-config
```
