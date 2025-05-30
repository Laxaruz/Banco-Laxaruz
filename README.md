# # 🏦 Banco Laxaruz - Sistema de Cajero Automático

<div align="center">

![Java](https://img.shields.io/badge/Java-17-007396?style=flat-square&logo=java&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.4.5-6DB33F?style=flat-square&logo=spring-boot&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?style=flat-square&logo=mysql&logoColor=white)
![Thymeleaf](https://img.shields.io/badge/Thymeleaf-3.x-005F0F?style=flat-square&logo=thymeleaf&logoColor=white)
![Maven](https://img.shields.io/badge/Maven-3.8-C71A36?style=flat-square&logo=apache-maven&logoColor=white)

Sistema bancario completo con interfaz web para operaciones de cajero automático y administración

</div>

---

## 📋 Descripción

Banco Laxaruz es un sistema completo de cajero automático desarrollado con *Spring Boot* que simula las operaciones bancarias fundamentales. El sistema incluye una interfaz web intuitiva para clientes y un panel administrativo para la gestión de cuentas y usuarios.

### ✨ Características Principales

- 🔐 *Sistema de autenticación seguro* con PIN numérico
- 💰 *Operaciones bancarias completas*: consultas, retiros, consignaciones y transferencias
- 👤 *Panel administrativo* para gestión de clientes y cuentas
- 🔒 *Seguridad avanzada*: bloqueo automático por intentos fallidos
- 📊 *Auditoría completa* con logging detallado
- 📱 *Interfaz responsive* adaptable a cualquier dispositivo
- 🎨 *UI moderna* con animaciones y efectos visuales
- 💳 *Soporte para múltiples tipos* de cuenta (Ahorros y Corriente)

---

## 🚀 Tecnologías Utilizadas

### Backend
- *Java 17* - Lenguaje de programación principal
- *Spring Boot 3.4.5* - Framework principal
- *Spring Data JPA* - Persistencia de datos
- *Hibernate* - ORM para base de datos
- *Lombok* - Reducción de código boilerplate

### Frontend
- *Thymeleaf* - Motor de plantillas
- *HTML5/CSS3* - Estructura y estilos
- *JavaScript ES6* - Interactividad
- *Font Awesome* - Iconografía

### Base de Datos
- *MySQL 8.0* - Sistema de gestión de base de datos
- *MySQL Connector/J* - Driver de conexión

### Herramientas de Desarrollo
- *Maven* - Gestión de dependencias
- *Spring Boot DevTools* - Desarrollo en caliente
- *Logback* - Sistema de logging avanzado

---

## 🏗 Arquitectura del Sistema


📦 Banco-Laxaruz
├── 🎮 Controller Layer
│   ├── CajeroController.java      # Operaciones de cajero
│   ├── AdminController.java       # Panel administrativo
│   └── ErrorController.java       # Manejo de errores
├── 🔧 Service Layer
│   ├── ClienteService.java        # Lógica de clientes
│   ├── CuentaService.java         # Lógica de cuentas
│   ├── MovimientoService.java     # Lógica de transacciones
│   └── RetiroService.java         # Lógica específica de retiros
├── 🗃 Repository Layer
│   ├── ClienteRepository.java     # Acceso a datos de clientes
│   ├── CuentaRepository.java      # Acceso a datos de cuentas
│   └── MovimientoRepository.java  # Acceso a datos de movimientos
├── 🏛 Entity Layer
│   ├── Cliente.java               # Entidad cliente
│   ├── Cuenta.java                # Entidad cuenta
│   ├── Movimiento.java            # Entidad movimiento
│   ├── TipoCuenta.java            # Enum tipos de cuenta
│   └── TipoMovimiento.java        # Enum tipos de movimiento
└── 🛠 Utility Layer
    └── AuditLogger.java           # Sistema de auditoría


---

## 🔐 Funcionalidades

### 👥 Para Clientes

| Función | Descripción | Validaciones |
|---------|-------------|--------------|
| 🔓 *Login* | Autenticación con número de cuenta y PIN | Bloqueo automático tras 3 intentos fallidos |
| 💵 *Consulta de Saldo* | Visualización del saldo actual en tiempo real | Verificación de permisos de cuenta |
| 💸 *Retiros* | Extracción de dinero con múltiplos de $1.000 | Validación de saldo disponible |
| 💰 *Consignaciones* | Depósito de dinero en la cuenta | Monto mínimo de $1.000 |
| 🔄 *Transferencias* | Envío de dinero entre cuentas | Verificación de cuenta destino |
| 📊 *Historial* | Consulta de movimientos detallados | Ordenados por fecha descendente |
| 🔑 *Cambio de PIN* | Modificación segura de credenciales | Validación de PIN actual |

### 👨‍💼 Para Administradores

| Función | Descripción |
|---------|-------------|
| 👤 *Gestión de Clientes* | Crear, modificar y consultar información de clientes |
| 🏦 *Gestión de Cuentas* | Apertura de cuentas de ahorros y corriente |
| 🔓 *Desbloqueo de Cuentas* | Rehabilitación de cuentas bloqueadas |
| 📈 *Reportes* | Visualización de actividad y transacciones |

---

## ⚙ Instalación y Configuración

### 📋 Prerrequisitos

- ☕ *Java 17* o superior
- 🗄 *MySQL 8.0* o superior
- 📦 *Maven 3.8* o superior
- 🌐 Navegador web moderno

### 🛠 Pasos de Instalación

1. *Clonar el repositorio*
   bash
   git clone https://github.com/tu-usuario/Banco-Laxaruz.git
   cd Banco-Laxaruz
   

2. *Configurar la base de datos*
   sql
   CREATE DATABASE laxaruz;
   CREATE USER 'laxaruz_user'@'localhost' IDENTIFIED BY 'tu_password';
   GRANT ALL PRIVILEGES ON laxaruz.* TO 'laxaruz_user'@'localhost';
   FLUSH PRIVILEGES;
   

3. *Configurar aplicación*
   properties
   # src/main/resources/application.properties
   spring.datasource.url=jdbc:mysql://localhost:3306/laxaruz
   spring.datasource.username=laxaruz_user
   spring.datasource.password=tu_password
   

4. *Ejecutar la aplicación*
   bash
   # Windows
   ./mvnw.cmd spring-boot:run
   
   # Linux/Mac
   ./mvnw spring-boot:run
   

5. *Acceder a la aplicación*
   - 🌐 *Cajero:* http://localhost:8080/cajero/login
   - ⚙ *Administración:* http://localhost:8080/admin

---

## 🖥 Uso del Sistema

### 👤 Acceso de Cliente

1. *Ingresar* número de cuenta y PIN
2. *Seleccionar* operación desde el menú principal
3. *Completar* la transacción siguiendo las instrucciones
4. *Revisar* el comprobante de la operación

### 👨‍💼 Acceso de Administrador

1. *Acceder* al panel administrativo
2. *Gestionar* clientes y cuentas según sea necesario
3. *Desbloquear* cuentas cuando sea requerido
4. *Monitorear* la actividad del sistema

---

## 📂 Estructura de la Base de Datos

### 🏗 Modelo Entidad-Relación

sql
Cliente (1) ←→ (N) Cuenta (1) ←→ (N) Movimiento

📊 Tablas Principales:
├── 👤 clientes
│   ├── id (PK)
│   ├── nombre
│   ├── identificacion (UNIQUE)
│   ├── pin
│   ├── bloqueado
│   └── intentos_fallidos
├── 🏦 cuentas  
│   ├── id (PK)
│   ├── numero (UNIQUE)
│   ├── saldo
│   ├── tipo (ENUM)
│   └── cliente_id (FK)
└── 📊 movimientos
    ├── id (PK)
    ├── fecha
    ├── tipo (ENUM)
    ├── monto
    └── cuenta_id (FK)


---

## 🔧 Configuración Avanzada

### 📝 Sistema de Logging

El sistema incluye un completo sistema de auditoría:

java
// Configuración en application.properties
logging.level.com.Laxaruz.Cajero=DEBUG
logging.file.name=logs/cajero-application.log
logging.pattern.file=%d{yyyy-MM-dd HH:mm:ss.SSS} [%thread] %-5level %logger{36} - %msg%n


### 🔒 Configuraciones de Seguridad

properties
# Tiempo de sesión
server.servlet.session.timeout=30m
server.servlet.session.cookie.http-only=true

# Páginas de error personalizadas
server.error.whitelabel.enabled=false
server.error.include-message=always


---

## 🧪 Testing

### 🚀 Ejecutar Pruebas

bash
# Ejecutar todas las pruebas
./mvnw test

# Ejecutar con cobertura
./mvnw clean test jacoco:report


### 📊 Cobertura de Código

Las pruebas cubren:
- ✅ Servicios de negocio
- ✅ Controladores web
- ✅ Repositorios de datos
- ✅ Validaciones de entrada

---

## 🤝 Contribución

### 📋 Guía de Contribución

1. *Fork* el proyecto
2. *Crear* una rama para tu feature (git checkout -b feature/AmazingFeature)
3. *Commit* tus cambios (git commit -m 'Add some AmazingFeature')
4. *Push* a la rama (git push origin feature/AmazingFeature)
5. *Abrir* un Pull Request

### 📝 Estándares de Código

- ☕ Seguir convenciones de Java
- 📝 Documentar métodos públicos
- ✅ Incluir pruebas unitarias
- 🎨 Mantener consistencia en UI

---

## 📞 Soporte y Contacto

### 🐛 Reportar Problemas

Si encuentras algún problema:

1. *Revisar* los logs en logs/cajero-application.log
2. *Verificar* la configuración de base de datos
3. *Crear* un issue en GitHub con detalles completos

---

## 📄 Licencia

Este proyecto está licenciado bajo la Licencia MIT - ver el archivo [LICENSE](LICENSE) para más detalles.

---

## 🙏 Agradecimientos

- 🌱 *Spring Framework Team* por el excelente framework
- 🎨 *Font Awesome* por los iconos
- 📚 *Comunidad Open Source* por las herramientas y librerías

---

<div align="center">

*⭐ Si este proyecto te fue útil, considera darle una estrella ⭐*

*Desarrollado con ❤ para la comunidad bancaria*

</div>
