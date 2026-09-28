# MikroTik — 12 jaulas · 2 cámaras

Configuración para 6 switches, 2 jaulas por switch y 2 cámaras por jaula (24 cámaras).

## Configuración

```routeros
/system reset-configuration no-defaults=yes skip-backup=yes
```

> Después del reinicio, volver a conectarse al MikroTik y continuar con los siguientes bloques.

### Bridge y puertos

```routeros
/interface bridge add name=bridge-lan
/interface bridge port add bridge=bridge-lan interface=ether1
/interface bridge port add bridge=bridge-lan interface=ether2
/interface bridge port add bridge=bridge-lan interface=ether3
/interface bridge port add bridge=bridge-lan interface=ether4
/interface bridge port add bridge=bridge-lan interface=ether5
/ip address add address=192.168.1.1/24 interface=bridge-lan
/ip address add address=192.168.100.1/24 interface=bridge-lan
```

### VLAN

```routeros
/interface vlan add name=vlan11 vlan-id=11 interface=bridge-lan
/interface vlan add name=vlan12 vlan-id=12 interface=bridge-lan
/interface vlan add name=vlan21 vlan-id=21 interface=bridge-lan
/interface vlan add name=vlan22 vlan-id=22 interface=bridge-lan
/interface vlan add name=vlan31 vlan-id=31 interface=bridge-lan
/interface vlan add name=vlan32 vlan-id=32 interface=bridge-lan
/interface vlan add name=vlan41 vlan-id=41 interface=bridge-lan
/interface vlan add name=vlan42 vlan-id=42 interface=bridge-lan
/interface vlan add name=vlan51 vlan-id=51 interface=bridge-lan
/interface vlan add name=vlan52 vlan-id=52 interface=bridge-lan
/interface vlan add name=vlan61 vlan-id=61 interface=bridge-lan
/interface vlan add name=vlan62 vlan-id=62 interface=bridge-lan
/interface vlan add name=vlan71 vlan-id=71 interface=bridge-lan
/interface vlan add name=vlan72 vlan-id=72 interface=bridge-lan
/interface vlan add name=vlan81 vlan-id=81 interface=bridge-lan
/interface vlan add name=vlan82 vlan-id=82 interface=bridge-lan
/interface vlan add name=vlan91 vlan-id=91 interface=bridge-lan
/interface vlan add name=vlan92 vlan-id=92 interface=bridge-lan
/interface vlan add name=vlan101 vlan-id=101 interface=bridge-lan
/interface vlan add name=vlan102 vlan-id=102 interface=bridge-lan
/interface vlan add name=vlan111 vlan-id=111 interface=bridge-lan
/interface vlan add name=vlan112 vlan-id=112 interface=bridge-lan
/interface vlan add name=vlan121 vlan-id=121 interface=bridge-lan
/interface vlan add name=vlan122 vlan-id=122 interface=bridge-lan
/interface vlan add name=vlan131 vlan-id=131 interface=bridge-lan
/interface vlan add name=vlan132 vlan-id=132 interface=bridge-lan
/interface vlan add name=vlan141 vlan-id=141 interface=bridge-lan
/interface vlan add name=vlan142 vlan-id=142 interface=bridge-lan
/interface vlan add name=vlan151 vlan-id=151 interface=bridge-lan
/interface vlan add name=vlan152 vlan-id=152 interface=bridge-lan
/interface vlan add name=vlan161 vlan-id=161 interface=bridge-lan
/interface vlan add name=vlan162 vlan-id=162 interface=bridge-lan
/interface vlan add name=vlan200 vlan-id=200 interface=bridge-lan
```

### Direcciones IP

```routeros
/ip address add address=192.168.11.1/24 interface=vlan11
/ip address add address=192.168.12.1/24 interface=vlan12
/ip address add address=192.168.21.1/24 interface=vlan21
/ip address add address=192.168.22.1/24 interface=vlan22
/ip address add address=192.168.31.1/24 interface=vlan31
/ip address add address=192.168.32.1/24 interface=vlan32
/ip address add address=192.168.41.1/24 interface=vlan41
/ip address add address=192.168.42.1/24 interface=vlan42
/ip address add address=192.168.51.1/24 interface=vlan51
/ip address add address=192.168.52.1/24 interface=vlan52
/ip address add address=192.168.61.1/24 interface=vlan61
/ip address add address=192.168.62.1/24 interface=vlan62
/ip address add address=192.168.71.1/24 interface=vlan71
/ip address add address=192.168.72.1/24 interface=vlan72
/ip address add address=192.168.81.1/24 interface=vlan81
/ip address add address=192.168.82.1/24 interface=vlan82
/ip address add address=192.168.91.1/24 interface=vlan91
/ip address add address=192.168.92.1/24 interface=vlan92
/ip address add address=192.168.101.1/24 interface=vlan101
/ip address add address=192.168.102.1/24 interface=vlan102
/ip address add address=192.168.111.1/24 interface=vlan111
/ip address add address=192.168.112.1/24 interface=vlan112
/ip address add address=192.168.121.1/24 interface=vlan121
/ip address add address=192.168.122.1/24 interface=vlan122
/ip address add address=192.168.131.1/24 interface=vlan131
/ip address add address=192.168.132.1/24 interface=vlan132
/ip address add address=192.168.141.1/24 interface=vlan141
/ip address add address=192.168.142.1/24 interface=vlan142
/ip address add address=192.168.151.1/24 interface=vlan151
/ip address add address=192.168.152.1/24 interface=vlan152
/ip address add address=192.168.161.1/24 interface=vlan161
/ip address add address=192.168.162.1/24 interface=vlan162
/ip address add address=192.168.200.1/24 interface=vlan200
```

### Pools DHCP

```routeros
/ip pool add name=pool11 ranges=192.168.11.2-192.168.11.2
/ip pool add name=pool12 ranges=192.168.12.2-192.168.12.2
/ip pool add name=pool21 ranges=192.168.21.2-192.168.21.2
/ip pool add name=pool22 ranges=192.168.22.2-192.168.22.2
/ip pool add name=pool31 ranges=192.168.31.2-192.168.31.2
/ip pool add name=pool32 ranges=192.168.32.2-192.168.32.2
/ip pool add name=pool41 ranges=192.168.41.2-192.168.41.2
/ip pool add name=pool42 ranges=192.168.42.2-192.168.42.2
/ip pool add name=pool51 ranges=192.168.51.2-192.168.51.2
/ip pool add name=pool52 ranges=192.168.52.2-192.168.52.2
/ip pool add name=pool61 ranges=192.168.61.2-192.168.61.2
/ip pool add name=pool62 ranges=192.168.62.2-192.168.62.2
/ip pool add name=pool71 ranges=192.168.71.2-192.168.71.2
/ip pool add name=pool72 ranges=192.168.72.2-192.168.72.2
/ip pool add name=pool81 ranges=192.168.81.2-192.168.81.2
/ip pool add name=pool82 ranges=192.168.82.2-192.168.82.2
/ip pool add name=pool91 ranges=192.168.91.2-192.168.91.2
/ip pool add name=pool92 ranges=192.168.92.2-192.168.92.2
/ip pool add name=pool101 ranges=192.168.101.2-192.168.101.2
/ip pool add name=pool102 ranges=192.168.102.2-192.168.102.2
/ip pool add name=pool111 ranges=192.168.111.2-192.168.111.2
/ip pool add name=pool112 ranges=192.168.112.2-192.168.112.2
/ip pool add name=pool121 ranges=192.168.121.2-192.168.121.2
/ip pool add name=pool122 ranges=192.168.122.2-192.168.122.2
/ip pool add name=pool131 ranges=192.168.131.2-192.168.131.2
/ip pool add name=pool132 ranges=192.168.132.2-192.168.132.2
/ip pool add name=pool141 ranges=192.168.141.2-192.168.141.2
/ip pool add name=pool142 ranges=192.168.142.2-192.168.142.2
/ip pool add name=pool151 ranges=192.168.151.2-192.168.151.2
/ip pool add name=pool152 ranges=192.168.152.2-192.168.152.2
/ip pool add name=pool161 ranges=192.168.161.2-192.168.161.2
/ip pool add name=pool162 ranges=192.168.162.2-192.168.162.2
/ip pool add name=pool200 ranges=192.168.200.2-192.168.200.10
```

### Servidores DHCP

```routeros
/ip dhcp-server add name=dhcp11 interface=vlan11 address-pool=pool11 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp12 interface=vlan12 address-pool=pool12 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp21 interface=vlan21 address-pool=pool21 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp22 interface=vlan22 address-pool=pool22 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp31 interface=vlan31 address-pool=pool31 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp32 interface=vlan32 address-pool=pool32 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp41 interface=vlan41 address-pool=pool41 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp42 interface=vlan42 address-pool=pool42 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp51 interface=vlan51 address-pool=pool51 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp52 interface=vlan52 address-pool=pool52 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp61 interface=vlan61 address-pool=pool61 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp62 interface=vlan62 address-pool=pool62 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp71 interface=vlan71 address-pool=pool71 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp72 interface=vlan72 address-pool=pool72 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp81 interface=vlan81 address-pool=pool81 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp82 interface=vlan82 address-pool=pool82 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp91 interface=vlan91 address-pool=pool91 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp92 interface=vlan92 address-pool=pool92 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp101 interface=vlan101 address-pool=pool101 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp102 interface=vlan102 address-pool=pool102 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp111 interface=vlan111 address-pool=pool111 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp112 interface=vlan112 address-pool=pool112 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp121 interface=vlan121 address-pool=pool121 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp122 interface=vlan122 address-pool=pool122 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp131 interface=vlan131 address-pool=pool131 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp132 interface=vlan132 address-pool=pool132 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp141 interface=vlan141 address-pool=pool141 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp142 interface=vlan142 address-pool=pool142 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp151 interface=vlan151 address-pool=pool151 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp152 interface=vlan152 address-pool=pool152 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp161 interface=vlan161 address-pool=pool161 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp162 interface=vlan162 address-pool=pool162 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp200 interface=vlan200 address-pool=pool200 lease-time=00:10:00 disabled=no
```

### Redes DHCP

```routeros
/ip dhcp-server network add address=192.168.11.0/24 gateway=192.168.11.1
/ip dhcp-server network add address=192.168.12.0/24 gateway=192.168.12.1
/ip dhcp-server network add address=192.168.21.0/24 gateway=192.168.21.1
/ip dhcp-server network add address=192.168.22.0/24 gateway=192.168.22.1
/ip dhcp-server network add address=192.168.31.0/24 gateway=192.168.31.1
/ip dhcp-server network add address=192.168.32.0/24 gateway=192.168.32.1
/ip dhcp-server network add address=192.168.41.0/24 gateway=192.168.41.1
/ip dhcp-server network add address=192.168.42.0/24 gateway=192.168.42.1
/ip dhcp-server network add address=192.168.51.0/24 gateway=192.168.51.1
/ip dhcp-server network add address=192.168.52.0/24 gateway=192.168.52.1
/ip dhcp-server network add address=192.168.61.0/24 gateway=192.168.61.1
/ip dhcp-server network add address=192.168.62.0/24 gateway=192.168.62.1
/ip dhcp-server network add address=192.168.71.0/24 gateway=192.168.71.1
/ip dhcp-server network add address=192.168.72.0/24 gateway=192.168.72.1
/ip dhcp-server network add address=192.168.81.0/24 gateway=192.168.81.1
/ip dhcp-server network add address=192.168.82.0/24 gateway=192.168.82.1
/ip dhcp-server network add address=192.168.91.0/24 gateway=192.168.91.1
/ip dhcp-server network add address=192.168.92.0/24 gateway=192.168.92.1
/ip dhcp-server network add address=192.168.101.0/24 gateway=192.168.101.1
/ip dhcp-server network add address=192.168.102.0/24 gateway=192.168.102.1
/ip dhcp-server network add address=192.168.111.0/24 gateway=192.168.111.1
/ip dhcp-server network add address=192.168.112.0/24 gateway=192.168.112.1
/ip dhcp-server network add address=192.168.121.0/24 gateway=192.168.121.1
/ip dhcp-server network add address=192.168.122.0/24 gateway=192.168.122.1
/ip dhcp-server network add address=192.168.131.0/24 gateway=192.168.131.1
/ip dhcp-server network add address=192.168.132.0/24 gateway=192.168.132.1
/ip dhcp-server network add address=192.168.141.0/24 gateway=192.168.141.1
/ip dhcp-server network add address=192.168.142.0/24 gateway=192.168.142.1
/ip dhcp-server network add address=192.168.151.0/24 gateway=192.168.151.1
/ip dhcp-server network add address=192.168.152.0/24 gateway=192.168.152.1
/ip dhcp-server network add address=192.168.161.0/24 gateway=192.168.161.1
/ip dhcp-server network add address=192.168.162.0/24 gateway=192.168.162.1
/ip dhcp-server network add address=192.168.200.0/24 gateway=192.168.200.1
```

### Distribución de puertos

```text
bridge-lan:
ether1 = enlace hacia switches del módulo
ether2 = NVR cámaras (192.168.1.100 recomendado)
ether3 = NVR cámaras (192.168.1.101 recomendado)
ether4 = NVR domos (192.168.100.100 recomendado)
ether5 = gestión / reserva
```

### Backup

```routeros
/system backup save name=config-12j-2c
```

### Verificación

```routeros
/ip address print
/ip dhcp-server print
/ip dhcp-server lease print
/ping 192.168.11.2
```
