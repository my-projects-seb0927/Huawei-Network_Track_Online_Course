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

## Protocolos comunes de la pila de protocolos TCP/IP
Define una serie de protocolos estándar
![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/ceda9138-74d0-4020-9be6-495121b733d9)

## Capa de aplicación
Se encarga de proporcionar interfaces para la aplicación de software de modo que las apliaciones puedan utilizar los servicios de red. Existen múltiples protocolos de esta capa.

### FTP
- Transfiere archivos de un host a otro para implementar la descarga y carga de archivos.
- Se adapta a la estructura cliente/servidor (C/S).
- Este puede configuarse de dos modos: Pasivo y proactivo
![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/b369498b-a48b-4edf-bf18-296c66f97f94)

### SFTP
- Transimte archivos usando **Secure Shell (SHH)**.
- Encripta la información de autenticación y los datos para transmitir, con un nivel de seguridad mas alto que FTP.
- Es un protocolo de canal único.
- Su número de puerto de destino por defecto es el 22.
![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/c395c096-c6f4-4fff-97f1-b47099a0ff8a)

### Telnet
- Proporciona servicios de conexión remota para una red, permitiendo majear dispositivos remotos a través de PC locles.
- Para esto, se conecta a un servidor Telnet a través de un programa del cliente Telnet, y los comeandos que se le ingresen al cliente Telnet los ejecuta el servicor Telnet.
- La información transmitida se encuentra en en texto sin formato.
![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/ed56999d-96f0-4b5c-90cc-128e4c8d7c3e)

### STelnet
- Es un servicio seguro de Telnet, ya que todos los datos intercambiados se encriptan y se implementan junto con SSH.
- El número de puerto de destino es 22 por defecto, y tiene las siguientes negocicaciones entre cliente y servidor:
  - Negociación de versión
  - Negociación de algoritmo
  - Intercambio de claves
  - Autenticación de usuario
  - Interacción de sesión
  ![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/d7590c9d-90ae-479e-88d8-b28683747a42)

### HTTP
- Es el mas usado.
- Se inventó principalmente para publicar y recibir páginas hechas con HTML.
- Número de puerto destino: 80
![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/ee67b58b-07df-4c43-9cd2-f5e237f6c2d0)

### HTTPS
- Igual que HTTP, pero seguro.
- Se le agrega un nuevo protocolo de seguridad de la capa de transporte (TLS) para permitir la autenticación de identidad, encriptación de datos, y verificación de integridad de datos.
- El número de puerto de destino es 443 
![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/31f0bd16-111a-4ee6-8bbb-511a53091005)

### DNS
- Se le llama sistema de nombres de dominio. Básicamente, si se ingresa "www.google.com", se accede al servicio de DNS para conocer la dirección IP del nombre de dominio del sitio web.
![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/e618b01e-1d9a-420b-8f7c-9547eccd93c0)

## Capa de transporte
- Recibe datos de un protocolo de la capa de aplicación, encapsula los datos con el corresponiente encabezado y ayuda a establecer una conexión extrempo a extremo

### TCP y UDP: Formatos de paquete
![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/bc67a86b-1c85-4237-ac5e-1adfacd6da82)

- TCP y UDP distinguen los diferentes servicios con el uso de diferentes números de puerto.
- El puerto de origen utilizado por un cliente se asigna aleatoriamente, y al puerto de destino lo especifica la aplicación del servidor.
![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/404f94e2-8339-4a5b-81a7-67b9482a7e8e)

## Capa de Red
Transmite datos de un host a otro. Envía paquetes dsde un host de origen a un host de destino, proporciona direcciones lógicas para dispositivos de red e implementa el enrutamienta y redirección de paquetes de datos.

### Encabezado del paquete IP
![image](https://github.com/my-projects-seb0927/Huawei-Network_Track_Online_Course/assets/83418390/4cda7f69-fa8e-4c51-a7ad-085bdbe15aca)

### Redirección del paquete









