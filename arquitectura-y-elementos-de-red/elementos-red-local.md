# Tema 2: Elementos de una red de área local

> Módulo Formativo 1 (MF0220_2) — Unidad Formativa 1 (UF0854)
> Instalación y configuración de los nodos de una red de área local

## 1. Características y funciones de una red local

Una red local es la interconexión de varios ordenadores y periféricos. Su extensión está limitada físicamente a un edificio o a un entorno de unos pocos kilómetros. Incluye tanto el hardware como el software necesario para la interconexión de los dispositivos y el tratamiento de la información.

**Principales características:**
- Tecnología broadcast (difusión) con medio de transmisión compartido
- Cableado específico
- Capacidad de transmisión entre 1 Mbps y 1 Gbps
- Extensión máxima no superior a 3 km (una FDDI puede llegar a 200 km)
- Uso de un medio de comunicación privado
- Simplicidad del medio de transmisión (coaxial, cables telefónicos, fibra óptica)
- Facilidad para efectuar cambios en hardware y software
- Gran variedad y número de dispositivos conectados
- Posibilidad de conexión con otras redes

> **Toda LAN requiere los mismos componentes básicos:** tarjeta de red, cableado, concentradores/switches y routers, entre otros.

## 2. Estaciones de trabajo y servidores

### Estación de trabajo
Equipo que facilita a los usuarios el acceso a los servidores y periféricos de la red. A diferencia de un ordenador aislado, tiene tarjeta de red y está conectado físicamente (por cable u otros medios) a la red, aprovechando los recursos y servicios disponibles.

### Servidor
Ordenador que comparte sus recursos hardware y software con los demás equipos de la red. Sus características clave son: potencia de cálculo, importancia de la información que almacena y conexión con los recursos que se desean compartir.

## 3. Arquitectura cliente/servidor

Modelo de aplicación distribuida en el que las tareas se reparten entre proveedores de recursos (servidores) y demandantes (clientes). El cliente hace peticiones y el servidor responde.

La separación cliente/servidor es **lógica**: el servidor no tiene por qué ejecutarse en una única máquina ni ser un único programa. Ejemplos de servidores específicos: servidores web, de archivos, de correo, etc. La arquitectura básica es siempre la misma, aunque el propósito varíe.

## 4. Tarjetas de red (NIC)

Los interfaces de red, llamados **NIC** (Network Interface Card), son elementos hardware que dotan a un dispositivo de la comunicación necesaria con el medio de red. Suelen ser tarjetas que se incrustan en el equipo, aunque hoy en día es habitual que vengan integradas en la propia placa base.

## 5. Equipos de conectividad

### 5.1. Paneles de conexión (patch panel)
Reúnen todo el cableado estructurado de la red, facilitando la conexión y desconexión de equipos a concentradores o conmutadores. Es un elemento puramente físico, sin electrónica, que simplifica el mantenimiento del cableado.

### 5.2. Repetidores
Regeneran y retemporizan la señal a nivel de bits para que pueda viajar más lejos. Son dispositivos simples: una entrada y una salida que amplifican la señal eléctrica. Existen también repetidores multipuerto, muy usados en redes inalámbricas para extender la cobertura.

### 5.3. Concentrador o hub
Funciona como un repetidor multipuerto: difunde la señal a todas las interfaces conectadas. Crea un punto de conexión central para el cableado y mejora la fiabilidad de la red, ya que el fallo de un cable no interrumpe el resto. El hub únicamente regenera y reenvía la señal por broadcast a todos los puertos, sin ningún tipo de inteligencia.

### 5.4. Puente (bridge)
Conecta dos segmentos de red de área local, filtrando el tráfico para que el tráfico local siga siendo local, mientras permite la conectividad con otros segmentos. Hoy en día sus funciones han sido asumidas por switches y routers; su uso actual se limita a segmentaciones por seguridad o análisis de tráfico.

### 5.5. Pasarelas (gateways)
Dispositivo que interconecta redes con protocolos y arquitecturas diferentes en todos los niveles de comunicación, traduciendo la información de un protocolo a otro. El gateway suele ser un equipo configurado para dar a la LAN acceso a una red exterior, normalmente mediante traducción de direcciones IP (**NAT**: Network Address Translation).

La técnica de **IP Masquerading** (enmascaramiento de IP) permite que varios equipos de una LAN compartan una única IP pública para salir a Internet.

### 5.6. Conmutador (switch)
Funciona como un puente pero con múltiples puertos (puente multipuerto). A diferencia del hub, toma decisiones a partir de las **direcciones MAC**: envía los datos solo al puerto donde está conectado el destino, en vez de reenviarlos a todos los puertos. Esto hace que las redes sean mucho más eficientes.

### 5.7. Encaminadores (routers)
Examina la información entrante y elige la mejor ruta a través de las redes, conmutándola hacia el puerto de salida adecuado. Dispone de al menos dos interfaces de red. A diferencia del switch (direcciones MAC), el router toma decisiones basadas en **direcciones de red o clases (IP)**.

También conecta distintas tecnologías (Ethernet–ADSL, fibra–Token Ring, etc.). Es el dispositivo de regulación de tráfico más importante en redes grandes: Internet es, en esencia, un conjunto de redes interconectadas mediante routers.

### 5.8. Comparativa rápida de equipos de conectividad

| Dispositivo | Nivel de decisión | Función principal |
|---|---|---|
| Repetidor | Bits (nivel físico) | Regenera/amplifica la señal |
| Hub | Bits (nivel físico) | Repetidor multipuerto, envía a todos los puertos |
| Bridge | Dirección MAC | Filtra tráfico entre 2 segmentos |
| Switch | Dirección MAC | Bridge multipuerto, envía solo al puerto destino |
| Router | Dirección IP / red | Elige la mejor ruta entre redes distintas |
| Gateway | Protocolo completo | Traduce entre protocolos/arquitecturas distintas |

## 6. Dispositivos y comunicaciones inalámbricas

La comunicación inalámbrica no usa un medio físico de propagación, sino modulación de ondas electromagnéticas a través del espacio. Los dispositivos físicos están solo en emisores y receptores: antenas, portátiles, tabletas, móviles, etc.

### WiFi (WLAN, IEEE 802.11)
- Alcance típico en hardware asequible: 100–150 metros
- Se necesita un punto de acceso (conectado al router) y un dispositivo WiFi en el equipo
- Conviene situar el punto de acceso en alto, evitando barreras (paredes, metal, puertas)
- La seguridad se aplica mediante encriptación: **WPA** es mucho más seguro que su predecesor **WEP**

## 7. Sistemas operativos de red (NOS)

Un sistema operativo de red (**NOS**: Network Operating System) es el software que permite interconectar ordenadores para acceder a servicios y recursos, creando así una red de ordenadores. Se puede añadir al sistema operativo del equipo o venir integrado con él (ejemplo histórico: NetWare de Novell). Hoy está integrado en prácticamente todos los sistemas operativos: Linux, Windows, macOS, Android, iOS, etc.

**Características genéricas:**
- Conecta todos los equipos y recursos de la red
- Gestión de usuarios centralizada
- Proporciona seguridad: valida accesos (claves, certificados, biometría) y aplica políticas de seguridad
- Coordina las funciones de red junto con las propias del equipo
- Comparte recursos, gestionando la coordinación y los privilegios
- Permite monitorizar y gestionar la red y sus componentes

**Componentes habituales:**
- **Servidores**: equipos con sistema operativo en red que ofrecen recursos a otros equipos
- **Clientes**: equipos conectados para trabajar en red; normalmente no comparten recursos
- **Dominios**: agrupación lógica de equipos con gestión centralizada desde una única ubicación; el servidor principal gestiona los recursos (protocolo habitual: LDAP)

## 8. Medios de transmisión: cableado estructurado

Las principales diferencias de rendimiento entre tipos de cable están en el ancho de banda permitido, la inmunidad frente a interferencias electromagnéticas y la atenuación (pérdida de señal según la distancia).

Existen tres tipos de cable principales para el interior de edificios o entre edificios: **par trenzado, coaxial y fibra óptica** (el coaxial no se recomienda para instalaciones nuevas, salvo TV/CATV).

### 8.1. Par trenzado

Es el tipo de cable más común en redes de área local. Surgió reutilizando el cableado de las redes telefónicas. Los pares se trenzan para reducir la **diafonía** (interferencia entre pares adyacentes). El cable estándar actual en LAN es el de 4 pares.

**Categorías de cable de pares trenzados:**

| Categoría | Tipo de cable | Terminadores | Uso típico |
|---|---|---|---|
| 3 | UTP | RJ11 (solo tlf.) / RJ45 | Voz analógica |
| 5e (Cat. 5) | UTP / STP | RJ45 / RJ49 | Ethernet 100/1000 |
| 6 | UTP / STP | RJ45 / RJ49 | Ethernet 1000 |
| 6a (en desarrollo) | UTP / STP | RJ45 / RJ49 | Ethernet ¿10.000? |
| 7 (no oficial) | STP | GG-45 (compatible RJ45) | Ethernet 10.000 |

> Errores comunes en la instalación: destrenzar una longitud excesiva en los conectores, apretar demasiado las bridas o doblar en exceso el cable.

**UTP (Unshielded Twisted Pair) — par trenzado no apantallado**
- Conector RJ-45; el más utilizado en redes de área local en Europa
- Ventajas: bajo coste y facilidad de manejo
- Desventajas: mayor tasa de error y limitación de distancia sin regeneración
- Cable ligero, flexible y de pequeño diámetro (típico 0,52 cm), fácil de instalar

**STP (Shielded Twisted Pair) — par trenzado apantallado**
- Conector RJ-49; el más utilizado en redes de área local en EE.UU.
- Cada par cubierto con malla metálica, más una lámina blindada para el conjunto
- La malla reduce la tasa de error, pero incrementa el coste, el peso y reduce la flexibilidad

### 8.2. Cable coaxial

Formado por un núcleo de cobre ("vivo") rodeado de un dieléctrico, una pantalla conductora (mallas de cobre y/o papel de aluminio) y una capa aislante exterior. Tiene alta inmunidad electromagnética y poca atenuación, siendo apto para grandes distancias/capacidades. Su uso está en declive por su grosor y dificultad de manejo.

- **Grueso**: alta capacidad y distancia, pero caro y grueso — norma Ethernet 10Base-5
- **Fino**: más barato y fino, conector BNC, peor rendimiento que el grueso — norma Ethernet 10Base-2

### 8.3. Fibra óptica

Excelente para transmisión de datos: gran ancho de banda, baja atenuación (permite grandes distancias sin repetidores), baja tasa de error (BER), inmunidad a interferencias electromagnéticas, alta seguridad y resistencia a corrosión/altas temperaturas. Sus desventajas son el coste de producción y la fragilidad en el manejo.

La fibra consta de un **núcleo** (transporta el haz luminoso por reflexión total interna) y una **cubierta** con menor índice de refracción que actúa de "jaula" para el haz.

- **Fibra monomodo**: baja apertura numérica, un solo modo de propagación; usada con láser (ILD) para grandes velocidades/distancias, hasta 40–160 km sin amplificadores
- **Fibra multimodo**: mayor apertura, varios modos de propagación; usada con LEDs, más económica y sencilla de implantar

### 8.4. Comparativa de cables

| Característica | Par trenzado (UTP) | Par trenzado blindado (STP) | Coaxial | Fibra óptica |
|---|---|---|---|---|
| Tecnología probada | Sí | Sí | Sí | Sí |
| Ancho de banda | Medio | Medio | Alto | Muy alto |
| Full duplex | Sí | Sí | Sí | Sí (por pares) |
| Distancia media | 100 m | 100 m | 500 m (Ethernet) | Multi: ~100 km / Mono: mucho más |
| Inmunidad electromagnética | Limitada | Media | Media | Alta |
| Seguridad | Baja | Baja | Media | Alta |
| Coste | Bajo | Medio | Medio | Alto |

### 8.5. Selección del tipo de cableado

Los cables de cobre y fibra dentro de un edificio deben ser resistentes al fuego, generar poco humo y ser retardantes de la llama (estándar IEC 332-1 o equivalente). En canalizaciones subterráneas necesitan protección adicional contra roedores, humedad, radiación UV, campos magnéticos y tensión.

**Se recomienda usar fibra óptica cuando:**
- El cableado une edificios diferentes (evita corrientes inducidas por diferencias de potencial entre tierras)
- Se requiere máxima seguridad en la red (el cobre es más fácil de interceptar)
- Se atraviesan atmósferas corrosivas para los metales
- Hay riesgo de interferencia eléctrica (motores, fluorescentes, equipos de alta tensión)

Si no se dan estas circunstancias, se recomienda **cobre**: es más barato en material, instalación e interfaces, y más fácil de modificar en paneles y empalmes. En instalaciones grandes es habitual combinar: fibra para tendidos principales (entre edificios y cableado vertical) y cobre para el cableado horizontal.

### 8.6. Canalizaciones

Distribuyen y soportan el cable entre la salida del área de trabajo y el cuarto de telecomunicaciones. Los cables se fijan con abrazaderas a intervalos de 4 metros.

Para evitar interferencias, la canalización de corrientes débiles (datos) debe mantenerse separada de las corrientes fuertes (eléctricas), y si se cruzan, deben hacerlo perpendicularmente.

### 8.7. Cableado de par trenzado con RJ45 (TIA/EIA-568B)

El conexionado del cable UTP con RJ45 está regulado por los estándares TIA/EIA-568B, que definen dos terminaciones: **T568A** (recomendada, históricamente ISDN/RDSI) y **T568B** (históricamente AT&T).

| Pin | T568A | Función Ethernet | T568B |
|---|---|---|---|
| 1 | Blanco/Verde | Emisión (+) | Blanco/Naranja |
| 2 | Verde | Emisión (-) | Naranja |
| 3 | Blanco/Naranja | Recepción (+) | Blanco/Verde |
| 4 | Azul | Sin uso / Bi-dirección 1 (+) | Azul |
| 5 | Blanco/Azul | Sin uso / Bi-dirección 1 (-) | Blanco/Azul |
| 6 | Naranja | Recepción (-) | Verde |
| 7 | Blanco/Marrón | Sin uso / Bi-dirección 2 (+) | Blanco/Marrón |
| 8 | Marrón | Sin uso / Bi-dirección 2 (-) | Marrón |

> Uso de los pares según tecnología: telefonía usa el par 1; Ethernet 10/100 usa los pares 2 y 3; Gigabit Ethernet usa todos; Token Ring usa los pares 1 y 3; FDDI, ATM y TP-PMD usan los pares 2 y 4.

---

## 📌 Resumen rápido para repasar

- Toda LAN necesita: tarjeta de red, cableado, electrónica de red (hub/switch/router)
- Estación de trabajo = accede a la red | Servidor = comparte recursos con la red
- Repetidor y hub trabajan a nivel de bits, sin inteligencia
- Bridge y switch deciden por dirección MAC; el switch es un bridge multipuerto
- Router decide por dirección IP/red; conecta redes y tecnologías distintas
- Gateway traduce entre protocolos distintos y suele hacer NAT/IP Masquerading
- WiFi = IEEE 802.11; seguridad recomendada: WPA (mejor que WEP)
- NOS (sistema operativo de red): conecta, gestiona usuarios, da seguridad y comparte recursos
- Par trenzado UTP = más usado en LAN (Europa, RJ-45); STP = apantallado (EE.UU., RJ-49)
- Fibra óptica: mayor ancho de banda, alcance y seguridad; monomodo (láser, largas distancias) vs. multimodo (LED, más barata)
- Norma de conexionado RJ45: TIA/EIA-568B (T568A recomendado / T568B)
