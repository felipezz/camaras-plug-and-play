# Runbook --- EdgeSwitch 8 (12 Jaulas · 2 Cámaras)

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
vlan 11,12,21,22,31,32,41,42,51,52,61,62,71,72,81,82,91,92,101,102,111,112,121,122,200
exit
```

------------------------------------------------------------------------

## □ Configurar puertos de cámara

Abrir el archivo correspondiente (`01-SW...md` a `06-SW...md`) y copiar
el bloque completo.

------------------------------------------------------------------------

## □ Configurar enlaces

``` text
configure

interface 0/9
vlan participation include 11,12,21,22,31,32,41,42,51,52,61,62,71,72,81,82,91,92,101,102,111,112,121,122,200
vlan tagging 11,12,21,22,31,32,41,42,51,52,61,62,71,72,81,82,91,92,101,102,111,112,121,122,200
vlan acceptframe all
exit

interface 0/10
vlan participation include 11,12,21,22,31,32,41,42,51,52,61,62,71,72,81,82,91,92,101,102,111,112,121,122,200
vlan tagging 11,12,21,22,31,32,41,42,51,52,61,62,71,72,81,82,91,92,101,102,111,112,121,122,200
vlan acceptframe all
exit
```

------------------------------------------------------------------------

## □ Finalizar

``` text
write memory

show running-config
```
