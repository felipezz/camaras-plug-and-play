# Nomenclatura

## Jaulas

Se elimina el prefijo `100`.

| Jaula | Número en red |
|---|---:|
| J101 | 1 |
| J102 | 2 |
| J108 | 8 |
| J110 | 10 |
| J116 | 16 |

## Cámaras

| Cámara | Número en red |
|---|---:|
| A | 1 |
| B | 2 |
| C | 3 |
| D | 4 |

## VLAN e IP

```text
VLAN = número de jaula + número de cámara
IP   = 192.168.<VLAN>.2
```

| Posición | VLAN | IP |
|---|---:|---|
| J101-A | 11 | `192.168.11.2` |
| J101-B | 12 | `192.168.12.2` |
| J102-A | 21 | `192.168.21.2` |
| J110-A | 101 | `192.168.101.2` |
| J116-D | 164 | `192.168.164.2` |
