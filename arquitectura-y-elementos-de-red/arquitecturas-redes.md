# Tema 1: Arquitecturas de redes de área local

> Instalación y configuración de los nodos de una red de área local

## 1. Clasificación de las redes según el territorio

Cuanto mayor es la zona que abarca una red, mayor es el tipo de red. Esta clasificación es la primera forma de entender qué tipo de red estamos viendo, ya que no es lo mismo conectar dos ordenadores en una misma habitación que conectar servidores situados en distintos países.

En todos los casos, lo que cambia es el alcance físico de la red y, con ello, la tecnología, el cableado y los dispositivos necesarios para que la comunicación sea posible. Cuando una red crece y empieza a interconectarse con otras a través de routers, deja de considerarse una simple LAN y pasa a formar parte de una red de mayor tamaño (MAN o WAN, según la distancia).

| Tipo | Nombre completo | Ámbito |
|------|------------------|--------|
| **PAN** | Personal Area Network | Alrededor de una persona (Bluetooth, infrarrojos) |
| **LAN** | Local Area Network | Vivienda, oficina, local, edificio |
| **CAN** | Campus Area Network | Campus universitario (se considera un tipo de MAN) |
| **MAN** | Metropolitan Area Network | Una ciudad |
| **WAN** | Wide Area Network | Grandes distancias (países, continentes) |

## 2. ¿Cómo es una red local?

Una LAN permite compartir recursos (impresoras, archivos, Internet) entre varios dispositivos.

**Componentes básicos:**
- **Electrónica de red**: router (acceso a Internet/otras redes) y switch (conecta los dispositivos entre sí)
- **Cableado de red**: medio físico por el que viajan los datos

## 3. Tipos de red según su funcionamiento

- **Red de grupo de trabajo**: sin servidor central, todos los equipos son iguales, cada uno se configura por separado.
- **Red cliente/servidor**: uno o varios servidores centralizan configuración, seguridad y recursos.

## 4. Topologías de red

La topología es la forma física y/o lógica en que se conectan los dispositivos.

### 4.1. Bus
Todos los equipos comparten un mismo cable.
- ✅ Todos se comunican por el mismo enlace
- ❌ Si se rompe el cable, la red se cae y es difícil localizar la avería
- ❌ Problemas de tráfico, colisiones y seguridad
- Usa **terminadores** en los extremos

### 4.2. Anillo
Los equipos forman un circuito cerrado, cada uno conectado a sus dos vecinos.
- Apenas se usa hoy en día
- Ejemplos: **Token Ring** (IBM), **FDDI**

### 4.3. Estrella
Todos los dispositivos se conectan a un nodo central (switch).
- ✅ Muy flexible: añadir/quitar equipos no afecta al resto
- ✅ Un fallo en un equipo no tumba la red
- ❌ Si falla el switch central, cae toda la red
- Es la **topología más usada actualmente** (Ethernet, WiFi)

### 4.4. Otras topologías
- **Anillo doble**: dos anillos concéntricos
- **Estrella extendida**: cada nodo de la estrella es a su vez centro de otra estrella
- **Árbol**: como estrella extendida, pero con un enlace troncal
- **Malla completa**: cada nodo conectado con todos los demás
- **Red celular**: áreas con nodo central (telefonía móvil)
- **Irregular**: sin patrón definido

## 5. Topología física vs. lógica

- **Física**: cómo está cableado realmente
- **Lógica**: cómo circulan realmente los datos

**Ejemplo clave: Ethernet** → topología física en **estrella**, pero funcionamiento lógico de **bus** (con concentrador).

## 6. Método de acceso al medio

Reglas que indican cuándo y cómo un equipo puede transmitir.

### 6.1. CSMA/CD (Ethernet)
1. El equipo escucha si el medio está libre
2. Si está libre, transmite
3. Si dos transmiten a la vez → colisión
4. Ambos paran y reintentan tras una espera

> Con el uso de **switches** las colisiones se reducen mucho → *Ethernet conmutada*

### 6.2. Token (testigo)
Un paquete especial (token) circula por la red. Solo quien lo tiene puede transmitir. Al terminar, lo libera al siguiente equipo.

## 7. Protocolos de comunicación

El "idioma común" que necesitan los dispositivos para entenderse. Estándar actual: **TCP/IP**.

| Tipo | Función | Ejemplo |
|------|---------|---------|
| **Protocolo enrutado** | Da la info para que los datos lleguen a su destino | IP |
| **Protocolo de enrutamiento** | Ayuda a los routers a decidir la mejor ruta | (RIP, OSPF, etc.) |

- Protocolos enrutados en desuso: **IPX** (Novell), **DDP** (AppleTalk)
- **NetBEUI**: no es enrutable, limitado a un solo segmento de red

## 8. Arquitecturas de redes LAN

Se definen según:
- **Técnica de transmisión**: difusión o punto a punto
- **Método de acceso**: CSMA o Token
- **Topología**: estrella, bus, anillo, mixta

**Difusión**: canal compartido, todas las máquinas "ven" los datos.
**Punto a punto**: conexiones entre pares de máquinas, más típico en MAN/WAN.

## 9. Normativa y estándares

Un **estándar** = normas técnicas documentadas para que equipos/fabricantes sean compatibles entre sí.

- **Organizaciones oficiales**: ITU, ISO, ANSI, IEEE, IETF, IEC
- **Consorcios de fabricantes**: más rápidos en sacar estándares al mercado

### IEEE 802 (los más importantes)

| Estándar | Contenido |
|----------|-----------|
| 802.1 | Gestión de red, interconexión |
| 802.2 | Control de enlace lógico (LLC) |
| **802.3** | **Ethernet** |
| 802.4 | Token Bus |
| 802.5 | Token-Passing Ring |
| 802.6 | Redes MAN |
| 802.9 | Integración voz y datos |
| 802.10 | Seguridad y privacidad |
| **802.11** | **WiFi** |
| 802.12 | Redes locales de alta velocidad |

## 10. Infraestructuras Comunes de Telecomunicación (ICT)

Conjunto de cables, equipos y canalizaciones que llevan los servicios (radio/TV, teléfono, banda ancha) hasta cada vivienda de un edificio.

**Obligatorio desde 1998** en edificios nuevos o rehabilitados integralmente.

### Evolución de la normativa ICT

- **1998** — Real Decreto-ley 1/1998: establece la obligación de dotar a los edificios de una infraestructura común de telecomunicaciones.
- **2003** — Real Decreto 401/2003: primer reglamento técnico completo (conocido como **ICT-I**), con las especificaciones de canalizaciones, recintos y cableado.
- **2011** — Real Decreto 346/2011: actualiza y amplía el reglamento anterior (conocido como **ICT-II**), adaptándolo a las nuevas tecnologías de banda ancha y fibra óptica. Se desarrolla mediante la Orden ITC/1644/2011.
- **2019** — Orden ECE/983/2019: actualiza los requisitos de reacción al fuego de los cables de telecomunicaciones en el interior de los edificios.

La ICT-II (RD 346/2011) es la normativa que sigue vigente en la actualidad.

### Zonas
- **Zona exterior**: fuera del edificio, hasta las arquetas
- **Zona común**: canalización de enlace (inferior = subterránea, superior = tejado/azotea)
- **Zona privada**: canalización interior de cada vivienda/local

### Tipos de red dentro de la ICT
1. **Red de alimentación**: lleva los servicios hasta los recintos del edificio
2. **Red de distribución**: reparte por la canalización principal
3. **Red de dispersión**: conecta distribución con la red interior de usuario
4. **Red interior de usuario**: dentro de la vivienda, normalmente en estrella

---

## 📌 Resumen rápido para repasar

- LAN pequeña, MAN ciudad, WAN grande distancia, PAN alrededor de una persona
- Estrella = topología más usada hoy, switch en el centro
- Ethernet = física estrella / lógica bus
- CSMA/CD: escuchar antes de transmitir, colisión → reintento
- TCP/IP = estándar actual de protocolos
- IP = protocolo enrutado; los de enrutamiento deciden rutas
- IEEE 802.3 = Ethernet | IEEE 802.11 = WiFi
- ICT = instalaciones de telecomunicaciones de un edificio (obligatorias desde 1998)
- Evolución normativa: 1998 (obligación) → 2003 ICT-I (RD 401/2003) → 2011 ICT-II (RD 346/2011, vigente) → 2019 actualización reacción al fuego
