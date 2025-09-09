# Para script Final\_system

# Sistema Store \& Forward

# Almacenamiento dual: Guarda datos en un archivo maestro y un buffer de envío

# 

# Recuperación inteligente: Reintenta el envío de datos pendientes automáticamente

# 

# Gestión de buffer: Elimina datos solo después de confirmación del servidor

# 

# ⏰ Sincronización de Tiempo

# RTC DS3231: Reloj de tiempo real de alta precisión

# 

# Intervalos configurables: Lecturas sincronizadas cada 5 minutos

# 

# Timestamp Unix: Marcas de tiempo con offset +3 horas (PY)

# 

# 🔧 Funciones de Mantenimiento

# Reinicio programado: Automático cada día a las 2:02 AM

# 

# Limpieza de buffer: Eliminación automática al inicializar

# 

# Log de eventos: Registro de reinicios y operaciones

# 

# 🛠️ Configuración Técnica

# Hardware Requerido

# Microcontrolador: ESP32

# 

# Sensor: Ultrasónico con interfaz Modbus RTU

# 

# Comunicación: Módem GPRS (Hardware Serial)

# 

# Almacenamiento: Tarjeta SD (SPI)

# 

# RTC: DS3231 (I2C)

# 

# Pines Utilizados

# Componente	Pines ESP32

# Módem GPRS	RX: 19, TX: 18

# Sensor Modbus	RX: 5, TX: 6

# Control DE/RE	Pin 7

# Tarjeta SD	CS: Pin 2

# Protocolos de Comunicación

# Modbus RTU: 9600 baudios, 8N1

# 

# Serial GPRS: 115200 baudios, 8N1

# 

# Formato datos: d=timestamp,valor

# 

# 📊 Flujo de Operación

# Lectura del Sensor: Cada 5 minutos mediante Modbus

# 

# Procesamiento: Conversión de mm a metros (3 decimales)

# 

# Almacenamiento:

# 

# Archivo maestro: datalog.csv (timestamp, valor)

# 

# Buffer de envío: buffer.csv (datos pendientes)

# 

# Transmisión: Envío automático al servidor

# 

# Confirmación: Eliminación del buffer solo tras confirmación

# 

# 🚀 Funciones Especiales

# Reinicio Programado

# cpp

# // Ejecuta diariamente a las 2:02 AM

# if (ahora.hour() == 2 \&\& ahora.minute() == 2) {

# &nbsp;   realizarReinicioSeguro();

# }

# Gestión de Buffer

# Eliminación de línea tras envío exitoso

# 

# Persistencia de datos en fallos de conexión

# 

# Archivo temporal para operaciones seguras

# 

# 📁 Estructura de Archivos en SD

# text

# /datalog.csv    # Log principal (timestamp, valor)

# /buffer.csv     # Datos pendientes de envío

# /reinicios.log  # Registro de reinicios automáticos

