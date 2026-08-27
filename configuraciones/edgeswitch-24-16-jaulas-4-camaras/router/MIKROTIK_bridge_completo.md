# MikroTik — 16 jaulas · 4 cámaras

## Resetear

```routeros
/system reset-configuration no-defaults=yes skip-backup=yes
```

Después del reinicio, volver a conectarse.

## Copiar y pegar

```routeros
/interface bridge add name=bridge-lan
/interface bridge port add bridge=bridge-lan interface=ether1
/interface bridge port add bridge=bridge-lan interface=ether2
/interface bridge port add bridge=bridge-lan interface=ether3
/interface bridge port add bridge=bridge-lan interface=ether4
/interface bridge port add bridge=bridge-lan interface=ether5

/ip address add address=192.168.1.1/24 interface=bridge-lan
/ip address add address=192.168.100.1/24 interface=bridge-lan

/interface vlan add name=vlan11 vlan-id=11 interface=bridge-lan
/interface vlan add name=vlan12 vlan-id=12 interface=bridge-lan
/interface vlan add name=vlan13 vlan-id=13 interface=bridge-lan
/interface vlan add name=vlan14 vlan-id=14 interface=bridge-lan
/interface vlan add name=vlan21 vlan-id=21 interface=bridge-lan
/interface vlan add name=vlan22 vlan-id=22 interface=bridge-lan
/interface vlan add name=vlan23 vlan-id=23 interface=bridge-lan
/interface vlan add name=vlan24 vlan-id=24 interface=bridge-lan
/interface vlan add name=vlan31 vlan-id=31 interface=bridge-lan
/interface vlan add name=vlan32 vlan-id=32 interface=bridge-lan
/interface vlan add name=vlan33 vlan-id=33 interface=bridge-lan
/interface vlan add name=vlan34 vlan-id=34 interface=bridge-lan
/interface vlan add name=vlan41 vlan-id=41 interface=bridge-lan
/interface vlan add name=vlan42 vlan-id=42 interface=bridge-lan
/interface vlan add name=vlan43 vlan-id=43 interface=bridge-lan
/interface vlan add name=vlan44 vlan-id=44 interface=bridge-lan
/interface vlan add name=vlan51 vlan-id=51 interface=bridge-lan
/interface vlan add name=vlan52 vlan-id=52 interface=bridge-lan
/interface vlan add name=vlan53 vlan-id=53 interface=bridge-lan
/interface vlan add name=vlan54 vlan-id=54 interface=bridge-lan
/interface vlan add name=vlan61 vlan-id=61 interface=bridge-lan
/interface vlan add name=vlan62 vlan-id=62 interface=bridge-lan
/interface vlan add name=vlan63 vlan-id=63 interface=bridge-lan
/interface vlan add name=vlan64 vlan-id=64 interface=bridge-lan
/interface vlan add name=vlan71 vlan-id=71 interface=bridge-lan
/interface vlan add name=vlan72 vlan-id=72 interface=bridge-lan
/interface vlan add name=vlan73 vlan-id=73 interface=bridge-lan
/interface vlan add name=vlan74 vlan-id=74 interface=bridge-lan
/interface vlan add name=vlan81 vlan-id=81 interface=bridge-lan
/interface vlan add name=vlan82 vlan-id=82 interface=bridge-lan
/interface vlan add name=vlan83 vlan-id=83 interface=bridge-lan
/interface vlan add name=vlan84 vlan-id=84 interface=bridge-lan
/interface vlan add name=vlan91 vlan-id=91 interface=bridge-lan
/interface vlan add name=vlan92 vlan-id=92 interface=bridge-lan
/interface vlan add name=vlan93 vlan-id=93 interface=bridge-lan
/interface vlan add name=vlan94 vlan-id=94 interface=bridge-lan
/interface vlan add name=vlan101 vlan-id=101 interface=bridge-lan
/interface vlan add name=vlan102 vlan-id=102 interface=bridge-lan
/interface vlan add name=vlan103 vlan-id=103 interface=bridge-lan
/interface vlan add name=vlan104 vlan-id=104 interface=bridge-lan
/interface vlan add name=vlan111 vlan-id=111 interface=bridge-lan
/interface vlan add name=vlan112 vlan-id=112 interface=bridge-lan
/interface vlan add name=vlan113 vlan-id=113 interface=bridge-lan
/interface vlan add name=vlan114 vlan-id=114 interface=bridge-lan
/interface vlan add name=vlan121 vlan-id=121 interface=bridge-lan
/interface vlan add name=vlan122 vlan-id=122 interface=bridge-lan
/interface vlan add name=vlan123 vlan-id=123 interface=bridge-lan
/interface vlan add name=vlan124 vlan-id=124 interface=bridge-lan
/interface vlan add name=vlan131 vlan-id=131 interface=bridge-lan
/interface vlan add name=vlan132 vlan-id=132 interface=bridge-lan
/interface vlan add name=vlan133 vlan-id=133 interface=bridge-lan
/interface vlan add name=vlan134 vlan-id=134 interface=bridge-lan
/interface vlan add name=vlan141 vlan-id=141 interface=bridge-lan
/interface vlan add name=vlan142 vlan-id=142 interface=bridge-lan
/interface vlan add name=vlan143 vlan-id=143 interface=bridge-lan
/interface vlan add name=vlan144 vlan-id=144 interface=bridge-lan
/interface vlan add name=vlan151 vlan-id=151 interface=bridge-lan
/interface vlan add name=vlan152 vlan-id=152 interface=bridge-lan
/interface vlan add name=vlan153 vlan-id=153 interface=bridge-lan
/interface vlan add name=vlan154 vlan-id=154 interface=bridge-lan
/interface vlan add name=vlan161 vlan-id=161 interface=bridge-lan
/interface vlan add name=vlan162 vlan-id=162 interface=bridge-lan
/interface vlan add name=vlan163 vlan-id=163 interface=bridge-lan
/interface vlan add name=vlan164 vlan-id=164 interface=bridge-lan
/interface vlan add name=vlan200 vlan-id=200 interface=bridge-lan

/ip address add address=192.168.11.1/24 interface=vlan11
/ip address add address=192.168.12.1/24 interface=vlan12
/ip address add address=192.168.13.1/24 interface=vlan13
/ip address add address=192.168.14.1/24 interface=vlan14
/ip address add address=192.168.21.1/24 interface=vlan21
/ip address add address=192.168.22.1/24 interface=vlan22
/ip address add address=192.168.23.1/24 interface=vlan23
/ip address add address=192.168.24.1/24 interface=vlan24
/ip address add address=192.168.31.1/24 interface=vlan31
/ip address add address=192.168.32.1/24 interface=vlan32
/ip address add address=192.168.33.1/24 interface=vlan33
/ip address add address=192.168.34.1/24 interface=vlan34
/ip address add address=192.168.41.1/24 interface=vlan41
/ip address add address=192.168.42.1/24 interface=vlan42
/ip address add address=192.168.43.1/24 interface=vlan43
/ip address add address=192.168.44.1/24 interface=vlan44
/ip address add address=192.168.51.1/24 interface=vlan51
/ip address add address=192.168.52.1/24 interface=vlan52
/ip address add address=192.168.53.1/24 interface=vlan53
/ip address add address=192.168.54.1/24 interface=vlan54
/ip address add address=192.168.61.1/24 interface=vlan61
/ip address add address=192.168.62.1/24 interface=vlan62
/ip address add address=192.168.63.1/24 interface=vlan63
/ip address add address=192.168.64.1/24 interface=vlan64
/ip address add address=192.168.71.1/24 interface=vlan71
/ip address add address=192.168.72.1/24 interface=vlan72
/ip address add address=192.168.73.1/24 interface=vlan73
/ip address add address=192.168.74.1/24 interface=vlan74
/ip address add address=192.168.81.1/24 interface=vlan81
/ip address add address=192.168.82.1/24 interface=vlan82
/ip address add address=192.168.83.1/24 interface=vlan83
/ip address add address=192.168.84.1/24 interface=vlan84
/ip address add address=192.168.91.1/24 interface=vlan91
/ip address add address=192.168.92.1/24 interface=vlan92
/ip address add address=192.168.93.1/24 interface=vlan93
/ip address add address=192.168.94.1/24 interface=vlan94
/ip address add address=192.168.101.1/24 interface=vlan101
/ip address add address=192.168.102.1/24 interface=vlan102
/ip address add address=192.168.103.1/24 interface=vlan103
/ip address add address=192.168.104.1/24 interface=vlan104
/ip address add address=192.168.111.1/24 interface=vlan111
/ip address add address=192.168.112.1/24 interface=vlan112
/ip address add address=192.168.113.1/24 interface=vlan113
/ip address add address=192.168.114.1/24 interface=vlan114
/ip address add address=192.168.121.1/24 interface=vlan121
/ip address add address=192.168.122.1/24 interface=vlan122
/ip address add address=192.168.123.1/24 interface=vlan123
/ip address add address=192.168.124.1/24 interface=vlan124
/ip address add address=192.168.131.1/24 interface=vlan131
/ip address add address=192.168.132.1/24 interface=vlan132
/ip address add address=192.168.133.1/24 interface=vlan133
/ip address add address=192.168.134.1/24 interface=vlan134
/ip address add address=192.168.141.1/24 interface=vlan141
/ip address add address=192.168.142.1/24 interface=vlan142
/ip address add address=192.168.143.1/24 interface=vlan143
/ip address add address=192.168.144.1/24 interface=vlan144
/ip address add address=192.168.151.1/24 interface=vlan151
/ip address add address=192.168.152.1/24 interface=vlan152
/ip address add address=192.168.153.1/24 interface=vlan153
/ip address add address=192.168.154.1/24 interface=vlan154
/ip address add address=192.168.161.1/24 interface=vlan161
/ip address add address=192.168.162.1/24 interface=vlan162
/ip address add address=192.168.163.1/24 interface=vlan163
/ip address add address=192.168.164.1/24 interface=vlan164
/ip address add address=192.168.200.1/24 interface=vlan200

/ip pool add name=pool11 ranges=192.168.11.2-192.168.11.2
/ip pool add name=pool12 ranges=192.168.12.2-192.168.12.2
/ip pool add name=pool13 ranges=192.168.13.2-192.168.13.2
/ip pool add name=pool14 ranges=192.168.14.2-192.168.14.2
/ip pool add name=pool21 ranges=192.168.21.2-192.168.21.2
/ip pool add name=pool22 ranges=192.168.22.2-192.168.22.2
/ip pool add name=pool23 ranges=192.168.23.2-192.168.23.2
/ip pool add name=pool24 ranges=192.168.24.2-192.168.24.2
/ip pool add name=pool31 ranges=192.168.31.2-192.168.31.2
/ip pool add name=pool32 ranges=192.168.32.2-192.168.32.2
/ip pool add name=pool33 ranges=192.168.33.2-192.168.33.2
/ip pool add name=pool34 ranges=192.168.34.2-192.168.34.2
/ip pool add name=pool41 ranges=192.168.41.2-192.168.41.2
/ip pool add name=pool42 ranges=192.168.42.2-192.168.42.2
/ip pool add name=pool43 ranges=192.168.43.2-192.168.43.2
/ip pool add name=pool44 ranges=192.168.44.2-192.168.44.2
/ip pool add name=pool51 ranges=192.168.51.2-192.168.51.2
/ip pool add name=pool52 ranges=192.168.52.2-192.168.52.2
/ip pool add name=pool53 ranges=192.168.53.2-192.168.53.2
/ip pool add name=pool54 ranges=192.168.54.2-192.168.54.2
/ip pool add name=pool61 ranges=192.168.61.2-192.168.61.2
/ip pool add name=pool62 ranges=192.168.62.2-192.168.62.2
/ip pool add name=pool63 ranges=192.168.63.2-192.168.63.2
/ip pool add name=pool64 ranges=192.168.64.2-192.168.64.2
/ip pool add name=pool71 ranges=192.168.71.2-192.168.71.2
/ip pool add name=pool72 ranges=192.168.72.2-192.168.72.2
/ip pool add name=pool73 ranges=192.168.73.2-192.168.73.2
/ip pool add name=pool74 ranges=192.168.74.2-192.168.74.2
/ip pool add name=pool81 ranges=192.168.81.2-192.168.81.2
/ip pool add name=pool82 ranges=192.168.82.2-192.168.82.2
/ip pool add name=pool83 ranges=192.168.83.2-192.168.83.2
/ip pool add name=pool84 ranges=192.168.84.2-192.168.84.2
/ip pool add name=pool91 ranges=192.168.91.2-192.168.91.2
/ip pool add name=pool92 ranges=192.168.92.2-192.168.92.2
/ip pool add name=pool93 ranges=192.168.93.2-192.168.93.2
/ip pool add name=pool94 ranges=192.168.94.2-192.168.94.2
/ip pool add name=pool101 ranges=192.168.101.2-192.168.101.2
/ip pool add name=pool102 ranges=192.168.102.2-192.168.102.2
/ip pool add name=pool103 ranges=192.168.103.2-192.168.103.2
/ip pool add name=pool104 ranges=192.168.104.2-192.168.104.2
/ip pool add name=pool111 ranges=192.168.111.2-192.168.111.2
/ip pool add name=pool112 ranges=192.168.112.2-192.168.112.2
/ip pool add name=pool113 ranges=192.168.113.2-192.168.113.2
/ip pool add name=pool114 ranges=192.168.114.2-192.168.114.2
/ip pool add name=pool121 ranges=192.168.121.2-192.168.121.2
/ip pool add name=pool122 ranges=192.168.122.2-192.168.122.2
/ip pool add name=pool123 ranges=192.168.123.2-192.168.123.2
/ip pool add name=pool124 ranges=192.168.124.2-192.168.124.2
/ip pool add name=pool131 ranges=192.168.131.2-192.168.131.2
/ip pool add name=pool132 ranges=192.168.132.2-192.168.132.2
/ip pool add name=pool133 ranges=192.168.133.2-192.168.133.2
/ip pool add name=pool134 ranges=192.168.134.2-192.168.134.2
/ip pool add name=pool141 ranges=192.168.141.2-192.168.141.2
/ip pool add name=pool142 ranges=192.168.142.2-192.168.142.2
/ip pool add name=pool143 ranges=192.168.143.2-192.168.143.2
/ip pool add name=pool144 ranges=192.168.144.2-192.168.144.2
/ip pool add name=pool151 ranges=192.168.151.2-192.168.151.2
/ip pool add name=pool152 ranges=192.168.152.2-192.168.152.2
/ip pool add name=pool153 ranges=192.168.153.2-192.168.153.2
/ip pool add name=pool154 ranges=192.168.154.2-192.168.154.2
/ip pool add name=pool161 ranges=192.168.161.2-192.168.161.2
/ip pool add name=pool162 ranges=192.168.162.2-192.168.162.2
/ip pool add name=pool163 ranges=192.168.163.2-192.168.163.2
/ip pool add name=pool164 ranges=192.168.164.2-192.168.164.2
/ip pool add name=pool200 ranges=192.168.200.2-192.168.200.10

/ip dhcp-server add name=dhcp11 interface=vlan11 address-pool=pool11 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp12 interface=vlan12 address-pool=pool12 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp13 interface=vlan13 address-pool=pool13 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp14 interface=vlan14 address-pool=pool14 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp21 interface=vlan21 address-pool=pool21 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp22 interface=vlan22 address-pool=pool22 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp23 interface=vlan23 address-pool=pool23 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp24 interface=vlan24 address-pool=pool24 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp31 interface=vlan31 address-pool=pool31 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp32 interface=vlan32 address-pool=pool32 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp33 interface=vlan33 address-pool=pool33 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp34 interface=vlan34 address-pool=pool34 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp41 interface=vlan41 address-pool=pool41 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp42 interface=vlan42 address-pool=pool42 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp43 interface=vlan43 address-pool=pool43 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp44 interface=vlan44 address-pool=pool44 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp51 interface=vlan51 address-pool=pool51 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp52 interface=vlan52 address-pool=pool52 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp53 interface=vlan53 address-pool=pool53 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp54 interface=vlan54 address-pool=pool54 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp61 interface=vlan61 address-pool=pool61 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp62 interface=vlan62 address-pool=pool62 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp63 interface=vlan63 address-pool=pool63 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp64 interface=vlan64 address-pool=pool64 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp71 interface=vlan71 address-pool=pool71 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp72 interface=vlan72 address-pool=pool72 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp73 interface=vlan73 address-pool=pool73 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp74 interface=vlan74 address-pool=pool74 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp81 interface=vlan81 address-pool=pool81 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp82 interface=vlan82 address-pool=pool82 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp83 interface=vlan83 address-pool=pool83 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp84 interface=vlan84 address-pool=pool84 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp91 interface=vlan91 address-pool=pool91 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp92 interface=vlan92 address-pool=pool92 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp93 interface=vlan93 address-pool=pool93 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp94 interface=vlan94 address-pool=pool94 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp101 interface=vlan101 address-pool=pool101 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp102 interface=vlan102 address-pool=pool102 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp103 interface=vlan103 address-pool=pool103 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp104 interface=vlan104 address-pool=pool104 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp111 interface=vlan111 address-pool=pool111 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp112 interface=vlan112 address-pool=pool112 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp113 interface=vlan113 address-pool=pool113 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp114 interface=vlan114 address-pool=pool114 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp121 interface=vlan121 address-pool=pool121 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp122 interface=vlan122 address-pool=pool122 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp123 interface=vlan123 address-pool=pool123 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp124 interface=vlan124 address-pool=pool124 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp131 interface=vlan131 address-pool=pool131 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp132 interface=vlan132 address-pool=pool132 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp133 interface=vlan133 address-pool=pool133 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp134 interface=vlan134 address-pool=pool134 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp141 interface=vlan141 address-pool=pool141 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp142 interface=vlan142 address-pool=pool142 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp143 interface=vlan143 address-pool=pool143 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp144 interface=vlan144 address-pool=pool144 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp151 interface=vlan151 address-pool=pool151 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp152 interface=vlan152 address-pool=pool152 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp153 interface=vlan153 address-pool=pool153 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp154 interface=vlan154 address-pool=pool154 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp161 interface=vlan161 address-pool=pool161 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp162 interface=vlan162 address-pool=pool162 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp163 interface=vlan163 address-pool=pool163 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp164 interface=vlan164 address-pool=pool164 lease-time=00:01:00 disabled=no
/ip dhcp-server add name=dhcp200 interface=vlan200 address-pool=pool200 lease-time=00:10:00 disabled=no

/ip dhcp-server network add address=192.168.11.0/24 gateway=192.168.11.1
/ip dhcp-server network add address=192.168.12.0/24 gateway=192.168.12.1
/ip dhcp-server network add address=192.168.13.0/24 gateway=192.168.13.1
/ip dhcp-server network add address=192.168.14.0/24 gateway=192.168.14.1
/ip dhcp-server network add address=192.168.21.0/24 gateway=192.168.21.1
/ip dhcp-server network add address=192.168.22.0/24 gateway=192.168.22.1
/ip dhcp-server network add address=192.168.23.0/24 gateway=192.168.23.1
/ip dhcp-server network add address=192.168.24.0/24 gateway=192.168.24.1
/ip dhcp-server network add address=192.168.31.0/24 gateway=192.168.31.1
/ip dhcp-server network add address=192.168.32.0/24 gateway=192.168.32.1
/ip dhcp-server network add address=192.168.33.0/24 gateway=192.168.33.1
/ip dhcp-server network add address=192.168.34.0/24 gateway=192.168.34.1
/ip dhcp-server network add address=192.168.41.0/24 gateway=192.168.41.1
/ip dhcp-server network add address=192.168.42.0/24 gateway=192.168.42.1
/ip dhcp-server network add address=192.168.43.0/24 gateway=192.168.43.1
/ip dhcp-server network add address=192.168.44.0/24 gateway=192.168.44.1
/ip dhcp-server network add address=192.168.51.0/24 gateway=192.168.51.1
/ip dhcp-server network add address=192.168.52.0/24 gateway=192.168.52.1
/ip dhcp-server network add address=192.168.53.0/24 gateway=192.168.53.1
/ip dhcp-server network add address=192.168.54.0/24 gateway=192.168.54.1
/ip dhcp-server network add address=192.168.61.0/24 gateway=192.168.61.1
/ip dhcp-server network add address=192.168.62.0/24 gateway=192.168.62.1
/ip dhcp-server network add address=192.168.63.0/24 gateway=192.168.63.1
/ip dhcp-server network add address=192.168.64.0/24 gateway=192.168.64.1
/ip dhcp-server network add address=192.168.71.0/24 gateway=192.168.71.1
/ip dhcp-server network add address=192.168.72.0/24 gateway=192.168.72.1
/ip dhcp-server network add address=192.168.73.0/24 gateway=192.168.73.1
/ip dhcp-server network add address=192.168.74.0/24 gateway=192.168.74.1
/ip dhcp-server network add address=192.168.81.0/24 gateway=192.168.81.1
/ip dhcp-server network add address=192.168.82.0/24 gateway=192.168.82.1
/ip dhcp-server network add address=192.168.83.0/24 gateway=192.168.83.1
/ip dhcp-server network add address=192.168.84.0/24 gateway=192.168.84.1
/ip dhcp-server network add address=192.168.91.0/24 gateway=192.168.91.1
/ip dhcp-server network add address=192.168.92.0/24 gateway=192.168.92.1
/ip dhcp-server network add address=192.168.93.0/24 gateway=192.168.93.1
/ip dhcp-server network add address=192.168.94.0/24 gateway=192.168.94.1
/ip dhcp-server network add address=192.168.101.0/24 gateway=192.168.101.1
/ip dhcp-server network add address=192.168.102.0/24 gateway=192.168.102.1
/ip dhcp-server network add address=192.168.103.0/24 gateway=192.168.103.1
/ip dhcp-server network add address=192.168.104.0/24 gateway=192.168.104.1
/ip dhcp-server network add address=192.168.111.0/24 gateway=192.168.111.1
/ip dhcp-server network add address=192.168.112.0/24 gateway=192.168.112.1
/ip dhcp-server network add address=192.168.113.0/24 gateway=192.168.113.1
/ip dhcp-server network add address=192.168.114.0/24 gateway=192.168.114.1
/ip dhcp-server network add address=192.168.121.0/24 gateway=192.168.121.1
/ip dhcp-server network add address=192.168.122.0/24 gateway=192.168.122.1
/ip dhcp-server network add address=192.168.123.0/24 gateway=192.168.123.1
/ip dhcp-server network add address=192.168.124.0/24 gateway=192.168.124.1
/ip dhcp-server network add address=192.168.131.0/24 gateway=192.168.131.1
/ip dhcp-server network add address=192.168.132.0/24 gateway=192.168.132.1
/ip dhcp-server network add address=192.168.133.0/24 gateway=192.168.133.1
/ip dhcp-server network add address=192.168.134.0/24 gateway=192.168.134.1
/ip dhcp-server network add address=192.168.141.0/24 gateway=192.168.141.1
/ip dhcp-server network add address=192.168.142.0/24 gateway=192.168.142.1
/ip dhcp-server network add address=192.168.143.0/24 gateway=192.168.143.1
/ip dhcp-server network add address=192.168.144.0/24 gateway=192.168.144.1
/ip dhcp-server network add address=192.168.151.0/24 gateway=192.168.151.1
/ip dhcp-server network add address=192.168.152.0/24 gateway=192.168.152.1
/ip dhcp-server network add address=192.168.153.0/24 gateway=192.168.153.1
/ip dhcp-server network add address=192.168.154.0/24 gateway=192.168.154.1
/ip dhcp-server network add address=192.168.161.0/24 gateway=192.168.161.1
/ip dhcp-server network add address=192.168.162.0/24 gateway=192.168.162.1
/ip dhcp-server network add address=192.168.163.0/24 gateway=192.168.163.1
/ip dhcp-server network add address=192.168.164.0/24 gateway=192.168.164.1
/ip dhcp-server network add address=192.168.200.0/24 gateway=192.168.200.1

# bridge-lan:
# ether1 = enlace hacia switches del módulo
# ether2 = NVR cámaras (192.168.1.100 recomendado)
# ether3 = NVR cámaras (192.168.1.101 recomendado)
# ether4 = NVR domos (192.168.100.100 recomendado)
# ether5 = gestión / reserva

/system backup save name=config-16j-4c
```

## Verificar

```routeros
/ip address print
/ip dhcp-server print
/ip dhcp-server lease print
/ping 192.168.11.2
```
