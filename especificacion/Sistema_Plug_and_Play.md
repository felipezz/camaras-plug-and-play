# Sistema de cámaras Plug & Play

> Especificación del sistema de cámaras submarinas Plug & Play.
> Este documento describe el funcionamiento, las condiciones y la implementación de referencia del sistema de cámaras Plug & Play utilizado por Jade.

---

# Objetivo

El sistema Plug & Play permite reemplazar una cámara submarina sin modificar la configuración del NVR.

Cuando una cámara falla, el proceso consiste en:

1. Desconectar la cámara dañada.
2. Conectar una cámara de reemplazo preparada para este sistema.
3. Esperar aproximadamente un minuto.

La imagen volverá automáticamente al mismo canal del NVR.

El objetivo es que el reemplazo de una cámara sea una tarea operativa, no una tarea de configuración.

---

# Cómo funciona

La identidad de una cámara no pertenece al equipo físico.

Pertenece a la posición donde se encuentra instalada.

Por esta razón, cada posición del centro posee permanentemente:

* un puerto del switch;
* una VLAN;
* una dirección IP.

El NVR siempre busca esa misma dirección IP.

Cuando una cámara preparada se conecta en esa posición, obtiene automáticamente la dirección correspondiente y ocupa nuevamente el mismo espacio dentro del NVR.

Gracias a esto, cambiar una cámara no requiere modificar el NVR ni recordar direcciones IP.

---

# Condiciones para el funcionamiento del sistema

El comportamiento Plug & Play depende de que todos los componentes trabajen bajo las mismas condiciones.

Estas condiciones no buscan hacer más compleja la instalación.

Su proposito es garantizar que cualquier cámara de reemplazo pueda comportarse exactamente igual que la cámara anterior.

## Preparación de cámaras

El funcionamiento Plug & Play supone que todas las cámaras utilizadas por el sistema han sido preparadas de la misma forma.

Una cámara preparada para este sistema posee:

* DHCP habilitado.
* ONVIF habilitado.
* Configuración de visualización compatible con el NVR
* Configuración revisada antes de enviarse a terreno.

Si una cámara no cumple estas condiciones, el reemplazo automático no está garantizado.

En ese caso, no es posible asegurar el comportamiento Plug & Play.

## Red

Cada posición conserva permanentemente:

* un puerto;
* una VLAN;
* una dirección IP.

La infraestructura puede crecer o reducirse según la cantidad de jaulas y cámaras, pero la relación entre posición, VLAN e IP se mantiene.

## Equipos

Los switches forman parte de la preparación del sistema y llegan al centro completamente configurados.

Su preparación considera:

* nombre del equipo;
* dirección de administración;
* rotulación;
* configuración lista para instalar.

El objetivo es que la configuración ocurra en taller y no durante la puesta en marcha.

---

# Implementación de referencia

Actualmente el sistema utiliza la siguiente implementación de referencia.

```text
Cámaras submarinas
        ↓
Switches del módulo
        ↓
Enlace principal
        ↓
Switch de oficina
   ├── NVR
   ├── NVR adicional (si corresponde)
   └── Router MikroTik
```

El enlace entre el módulo y la oficina puede llegar mediante:

* fibra directamente al switch de oficina;
* fibra hacia un conversor y posteriormente Ethernet al switch de oficina.

En ambos casos, el puerto que recibe el enlace debe transportar correctamente las VLAN utilizadas por el sistema.

La implementación puede evolucionar con el tiempo siempre que mantenga el mismo comportamiento operativo del sistema.

---

# Nomenclatura

La nomenclatura permite identificar cada posición del sistema de forma inmediata.

## Jaulas

Se elimina el prefijo `100`.

| Jaula | Número |
| ----- | -----: |
| J101  |      1 |
| J102  |      2 |
| ...   |    ... |
| J116  |     16 |

## Cámaras

| Cámara | Número |
| ------ | -----: |
| A      |      1 |
| B      |      2 |
| C      |      3 |
| D      |      4 |

## VLAN

La VLAN corresponde al número de la jaula seguido del número de la cámara.

Ejemplos:

| Posición | VLAN |
| -------- | ---: |
| J101-A   |   11 |
| J101-B   |   12 |
| J108-C   |   83 |
| J116-D   |  164 |

## Dirección IP

Cada VLAN posee una única dirección utilizada por la cámara.

Ejemplo:

| Posición | Dirección     |
| -------- | ------------- |
| J101-A   | 192.168.11.2  |
| J108-C   | 192.168.83.2  |
| J116-D   | 192.168.164.2 |

Gracias a esta nomenclatura es posible deducir la VLAN y la dirección IP únicamente conociendo la posición física de la cámara.

---

# Preparación e instalación

La preparación del sistema considera la verificación de:

* cantidad de jaulas;
* cámaras por jaula;
* cantidad de NVR necesarios;
* modelo y cantidad de switches;
* cámaras y repuestos preparados;
* etiquetas disponibles.

Cada switch del módulo atiende dos jaulas.

Las cámaras siempre ocupan el mismo orden de puertos.

La configuración correspondiente a cada variante del sistema se encuentra en la carpeta `configuraciones/`.

---

# Validación

Una instalación no se considera finalizada únicamente porque todas las cámaras muestran imagen.

La validación del sistema consiste en comprobar que el comportamiento Plug & Play funciona correctamente mediante una prueba de reemplazo.

La prueba consiste en:

1. Verificar la imagen de una cámara.
2. Desconectarla.
3. Conectar una cámara de reemplazo preparada.
4. Esperar aproximadamente un minuto.
5. Confirmar que la imagen vuelve al mismo canal del NVR sin realizar ninguna configuración adicional.

Si esta prueba es satisfactoria, el sistema se considera correctamente implementado.

---

# Diagnóstico

Cuando el comportamiento esperado no se obtiene, el primer paso consiste en verificar que el sistema continúa cumpliendo las condiciones descritas en este documento.

Habitualmente, la causa se encuentra en alguna de las siguientes condiciones:

* cámaras preparadas de forma distinta;
* cambios en la infraestructura de red;
* configuraciones modificadas fuera del procedimiento habitual.

Antes de modificar el NVR o realizar cambios en la red, conviene comprobar que las condiciones de funcionamiento descritas anteriormente continúan presentes.

---

# Filosofía del sistema

El objetivo del sistema Plug & Play no es únicamente automatizar la asignación de direcciones IP.

Su objetivo es ofrecer una experiencia repetible.

Cada centro se organiza de la misma manera.

Cada posición puede identificarse de forma inmediata.

Cada cámara preparada se comporta igual cuando reemplaza a otra.

Mientras estas condiciones se mantengan, el sistema seguirá siendo fácil de instalar, mantener y ampliar, independientemente de quién realice el trabajo.

