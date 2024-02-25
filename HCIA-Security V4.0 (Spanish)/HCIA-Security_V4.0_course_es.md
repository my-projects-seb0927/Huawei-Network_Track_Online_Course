# HCIA-Security V4.0 (Spanish)

¡Bienvenido! Aquí encontrarás mis apuntes sobre este curso de Huawei en español. Sientete bienvenido de explorar y/o usar estas notas para lo que necesites.

# Aspectos básicos de redes

## Modelo de referencia de red 

### Aplicaciones y datos
- Las aplicaciones se desarrollan para cumplir con los diferentes requisitos de los usuarios, tales como acceso de página web, videojuegos en línea, entre otros.
  - Esto trae consigo el manejo de todo tipo de información (Imágenes, vídeos, textos, símbolos, etc.)
- Estos datos deben de ser transmitios entre dispositivos, por lo que la atención se va al proceso de transmisión de datos de extremo a extremo.

### Modelo de referencia OSI
| **Capa**                | **Función**                                                                                                                                                                        |
|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|   Capa de aplicación    | Provee interfaces de red para aplicaciones.                                                                                                                                        |
|   Capa de presentación  | Convierte formatos de datos para garantizar que los datos de la capa de aplicación de un sistema puedan ser identificados y comprendidos por la capa de aplicación de otro sistema |
|   Capa se sesión        | Crea, gestiona y finaliza sesiones entre las partes comunicantes.                                                                                                                  |
| Capa de transporte      | Crea, mantiene y cancela el proceso de transmisión de datos de extremo a extremo. Controla la velocidad de transmisión y ajusta las secuencias de datos.                           |
| Capa de red             | Define direcciones lógicas y transfiere información del origen al punto de destino.                                                                                                |
| Capa de enlace de datos | Encapsula paquetes en tramas, transmite tramas en modos de punto a punto o punto a multipunto e implementa la detección de errores.                                                |
|  Capa física            | Transmite flujos de bits a través de un medio de transmisión y define las especificaciones eléctricas y físicas.                                                                   |

### Modelo de referencia TCP/IP
Este se ha convertido en el modelo de referencia real de Internet
![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/96660265-0c81-454f-9545-c52595813981)

### Protocolos comunes de la pila de protocolos TCP/IP
Define una serie de protocolos estándar
![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/ceda9138-74d0-4020-9be6-495121b733d9)

### Capa de aplicación
Se encarga de proporcionar interfaces para la aplicación de software de modo que las apliaciones puedan utilizar los servicios de red. Existen múltiples protocolos de esta capa.

#### FTP
- Transfiere archivos de un host a otro para implementar la descarga y carga de archivos.
- Se adapta a la estructura cliente/servidor (C/S).
- Este puede configuarse de dos modos: Pasivo y proactivo

![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/b369498b-a48b-4edf-bf18-296c66f97f94)

#### SFTP
- Transimte archivos usando **Secure Shell (SHH)**.
- Encripta la información de autenticación y los datos para transmitir, con un nivel de seguridad mas alto que FTP.
- Es un protocolo de canal único.
- Su número de puerto de destino por defecto es el 22.

![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/c395c096-c6f4-4fff-97f1-b47099a0ff8a)

#### Telnet
- Proporciona servicios de conexión remota para una red, permitiendo majear dispositivos remotos a través de PC locles.
- Para esto, se conecta a un servidor Telnet a través de un programa del cliente Telnet, y los comeandos que se le ingresen al cliente Telnet los ejecuta el servicor Telnet.
- La información transmitida se encuentra en en texto sin formato.

![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/ed56999d-96f0-4b5c-90cc-128e4c8d7c3e)

#### STelnet
- Es un servicio seguro de Telnet, ya que todos los datos intercambiados se encriptan y se implementan junto con SSH.
- El número de puerto de destino es 22 por defecto, y tiene las siguientes negocicaciones entre cliente y servidor:
  - Negociación de versión
  - Negociación de algoritmo
  - Intercambio de claves
  - Autenticación de usuario
  - Interacción de sesión
  
![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/d7590c9d-90ae-479e-88d8-b28683747a42)

#### HTTP
- Es el mas usado.
- Se inventó principalmente para publicar y recibir páginas hechas con HTML.
- Número de puerto destino: 80

![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/ee67b58b-07df-4c43-9cd2-f5e237f6c2d0)

#### HTTPS
- Igual que HTTP, pero seguro.
- Se le agrega un nuevo protocolo de seguridad de la capa de transporte (TLS) para permitir la autenticación de identidad, encriptación de datos, y verificación de integridad de datos.
- El número de puerto de destino es 443

![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/31f0bd16-111a-4ee6-8bbb-511a53091005)

#### DNS
Se le llama sistema de nombres de dominio. Básicamente, si se ingresa "www.google.com", se accede al servicio de DNS para conocer la dirección IP del nombre de dominio del sitio web.
  
![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/e618b01e-1d9a-420b-8f7c-9547eccd93c0)

### Capa de transporte
- Recibe datos de un protocolo de la capa de aplicación, encapsula los datos con el corresponiente encabezado y ayuda a establecer una conexión extrempo a extremo

#### TCP y UDP: Formatos de paquete
![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/bc67a86b-1c85-4237-ac5e-1adfacd6da82)

- TCP y UDP distinguen los diferentes servicios con el uso de diferentes números de puerto.
- El puerto de origen utilizado por un cliente se asigna aleatoriamente, y al puerto de destino lo especifica la aplicación del servidor.

![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/404f94e2-8339-4a5b-81a7-67b9482a7e8e)

### Capa de Red
Transmite datos de un host a otro. Envía paquetes dsde un host de origen a un host de destino, proporciona direcciones lógicas para dispositivos de red e implementa el enrutamienta y redirección de paquetes de datos.

#### Encabezado del paquete IP
![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/4cda7f69-fa8e-4c51-a7ad-085bdbe15aca)

#### Redirección del paquete
El encabezado de la capa de red de un paquete enviado por un dispositivo de origen lleva la dirección de la capa de red de los dispositivos de origen y de destino. Cada dispositivo de red (como un router) con funciones de enrutamiento cuenta con una tabla de enrutamiento. Luego de recibir un paquete, el dispositivo de red lee la dirección de destino de la capa de red del paquete, busca una coincidencia para la dirección en la tabla de enrutamiento y reenvía el paquete de acuerdo con las instrucciones de la coincidencia. 

![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/0074e53d-3cc6-457f-8d16-0c4c04c93ed7)

#### ICMP
- Protocolo de mensajes de control de Internet. Es un protocol IP auxiliar
- Se usa para transmitir errores y controlar información entre dispositivos de red.
- Obtiene información de red, así como de diagnostico y rectificación de fallas de red, tiene en sus respuestas tales como "Respuesta eco", "Red inalcanzable", entre otras.

### Comprobar errores de ICMP
- El mensaje de petición eco ICMP y el mensaje de respuesta eco ICMP por lo general se utilizan para chequear la conectividad de la red entre las direcciones de origen y destino, y obtener información del retardo.
- **Comando:** `ping`. Aquí se comprueban si los paquetes se encuentran llegando no. Ej: `ping 20.0.0.2`

### Informe de errores del protocolo ICMP
- El protocolo ICMP clasifica los diferentes mensajes de error para diagnosticar las fallas de conectividad de la red. Basado en los mensajes de error, el dispositivo de origen puede determinar la causa en la falla de transmisión de datos.
- **Comando:** `Tracert`. Rastrea la ruta de redirección del paquete salto a salto basándose en el valor del perído de vida del encabezado del paquete: Ej `tracert 20.0.0.2`.

#### OSPF
- Protocolo de enrutamiento dinámico mayormente utilizado en las redes empresariales.
- Básicamente, si se conecta un computador a la red, que a ese computador se le asigne una ruta de manera automática

#### Área OSPF
- El ID de un área OSPF se usa para identificar un área OSPF.
- Se considera a un área OSPF como un grupo lógico de dispositivos.
- La conexión de redes de área única o múltiple puede ser utilizada en empresas que se basan en escalas
y requisitos.

![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/f959061c-cba0-4c08-9bbb-afc0decd0997)

#### Tabla de enrutamiento OSPF
- Contiene la información utilizada para guiar la retransmisión de paquetes, incluyendo la dirección de destino, costo y el siguiente en salto.
- Se puede ejecutar con el comando: `display ospf routing` para verificar la información sobre la tabla de enrutamiento

#### Capa de enlace de datos
Provee servicios para protocolos como IP e IPv6 en la capa de red. El mas común es Ethernet.
- Proporciona comunicación intrasegmento para la capa de red.
- Incluyen entre sus funciones: entramado, dirección física, y control de errores.

#### Esctuctura de trama Ethernet.
- Hay dos formatos: Ethernet II e IEEE 802.3
- Una dirección de control de acceso a medios (MAC) identifica exclusivamente una tarjeta de interfaz de red (NIC). Las direcciones MAC son utilizadas para la comunicación intrasegmento, con 48 bits de longitud, tales como 00-1E-10-DD-DD-02.
![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/cf4c1b1c-8790-4cc2-9d19-b285ad333166)

#### ARP
Es un protocolo de resolución de direcciones, pero se utiliza para obtener la dirección MAC correspondiente con base en la dirección IP conocida.

#### Encapsulación de datos de un remitente
![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/7103f5b2-4ff7-4c65-a300-b16b83bf5e0b)

#### Desencapculación de datos de un receptor
![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/e29205ed-ee17-42fb-95f6-1f365cfb9ad5)

## Dispositivos de red comunes

### Switch
- Dispositivo mas próximo al usuario final y se usa para conectar terminales a la red y habilitar el reenvío de tramas de datos en el mismo segmento de red.
- Funcinan en la **capa de enlace de datos** y reenvían tramas de datos basándose en tablas de dirección MAC que almacenan el mapeo entre las direcciones MAC Y los puertos del switch.
- Crean LANs

### Router
- Los routers funcionan en la capa de red para garantizar que los paquetes puedan reenviarse entre las diferentes redes.
- Conectan redes.

### Firewall
- Se implementan mayoritariamente en las fronteras de la red para controlar los comportamientos de acceso a la red con protección de seguridad como característica principal.

Existe una tabla con la información de la zona y la prioridad de seguridad predeterminada:
| **Zona**           | **Prioridad de seguridad predeterminada**                                                     |
|--------------------|-----------------------------------------------------------------------------------------------|
| Zona no confiable  | 5 (Nivel de seguridad bajo)                                                                   |
| DMZ                | 50 (Nivel de seguridad medio)                                                                 |
| Zona de confianza  | 85 (Nivel de seguridad alto)                                                                  |
| Zona local         |  100 (Nivel de seguridad más alto). Una zona local define el dispositivo e incluye interfaces |

#### Funciones del firewall
Los firewalls protegen a la red contra ataques e intrusiones de otra red. Con atributos de aislamiento y defensa, los firewalls se implementan en las subidas de red empresarial, fronteras de subred de redes de amplia escala y fronteras del centro de datos (DC).
![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/4e565056-051e-4923-a713-902cffcfa850)

Los firewalls se implementan en las fronteras de las redes. Se encargan del control de acceso a la red

#### Inicio de sesión en el dispositivo de red y configuraciones
Aquí solo voy a poner los comandos del CLI:

- Configurar una dirección IP de intefaz:
  ```
  [FW] interface GigabitEthernet 0/0/1
  [FW-GigabitEthernet0/0/1]  ip address 10.102.0.1 255.255.255.0
  ```
- Ver las configuraciones actuales
  ```
  <FW> display current-configuration
  ```
- Guardar un archivo de configuración
  ```
  <FW> save
  ```
- Visualizar datos de configuración guardados
  ```
  <FW> display saved-configuration
  ```
- Borrar datos de configuración guardados
  ```
  <FW> reset saved-configuration
  ```
- Ver los parámetros de configuracion de puesta en marcha del sistema
  ```
  <FW> display startup
  ```
- Configurar el archivo de configuración para la próxima puesta en marcha
  ```
  <FW> startup saved-configuration *configuration-file*
  ```
- Reiniciar el dispositivo
  ```
  <FW> reboot
  ```

## Cuestionario
1. (Pregunta de respueta múltiple) ¿Cuále de los siguientes protocolos puede aplicarse a la capa de aplicación?
  - HTTP ✅
  - DNS ✅
  - FTP ✅
  - OSPF
2. (Verdadero o falso) La conexión de datos la inicia el cliente en modo FTP activo.
  - Verdadero
  - Falso ✅
