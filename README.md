# 🛒 ElectrodoStore - Arquitectura de Microservicios

## 📌 Descripción
ElectrodoStore es una aplicación backend basada en arquitectura de microservicios diseñada para la gestión de una tienda de productos electrónicos. El sistema permite administrar productos, clientes, carrito de compras y ventas, siguiendo principios de escalabilidad, desacoplamiento y resiliencia.

Este proyecto implementa los principales patrones de Spring Cloud con el objetivo de simular un entorno real de sistemas distribuidos.

---

## 🧱 Arquitectura

El sistema está compuesto por múltiples microservicios independientes, cada uno enfocado en una responsabilidad específica:

| Servicio | Descripción | Repo |
|---|---|---|
| `producto-service` | Gestión de productos | [🔗 ver repo](https://github.com/electrodostore/producto-service) |
| `cliente-service` | Gestión de clientes | [🔗 ver repo](https://github.com/electrodostore/cliente-service) |
| `carrito-service` | Carrito de compras | [🔗 ver repo](https://github.com/electrodostore/carrito-service) |
| `venta-service` | Procesamiento de ventas | [🔗 ver repo](https://github.com/electrodostore/venta-service) |
| `api-gateway` | Punto de entrada | [🔗 ver repo](https://github.com/electrodostore/api-gateway) |
| `eureka-server` | Service Discovery | [🔗 ver repo](https://github.com/electrodostore/eureka-server) |
| `config-server` | Config centralizada | [🔗 ver repo](https://github.com/electrodostore/config-server) |


> 🗂️ Las configuraciones de todos los servicios se gestionan de forma
> centralizada en un repositorio dedicado → [config-repo](https://github.com/electrodostore/electrodostore-config-server-repo)

---

## ⚙️ Tecnologías utilizadas

- Java + Spring Boot  
- Spring Cloud  
- Spring Cloud Gateway  
- Eureka (Service Discovery)  
- OpenFeign (Comunicación entre servicios)  
- Circuit Breaker (Resiliencia)  
- Docker & Docker Compose  
- MySQL  

---

## 🧩 Patrones de Microservicios implementados

Este proyecto implementa los principales patrones de arquitectura distribuida:

- **API Gateway** → Centraliza el acceso a los microservicios  
- **Service Discovery (Eureka)** → Permite ubicar dinámicamente los servicios  
- **Config Server** → Manejo centralizado de configuraciones  
- **Load Balancing** → Distribución de tráfico entre instancias  
- **Circuit Breaker** → Tolerancia a fallos y resiliencia  

---

## 🔗 Comunicación entre servicios

Los microservicios se comunican mediante:

- **REST APIs**  
- **Spring Cloud OpenFeign**  
- **Descubrimiento dinámico usando Eureka**  

---

## 🗄️ Base de datos

Cada microservicio posee su propia base de datos independiente (MySQL), siguiendo el principio de **Database per Service**, lo cual mejora el desacoplamiento y la escalabilidad del sistema.

---

## 🐳 Despliegue

El sistema está completamente dockerizado y puede ejecutarse en entorno local utilizando Docker Compose.

### ⚠️ Configuración previa

Antes de ejecutar el proyecto, debes crear un archivo `.env` basado en `.env.example` y completar las variables de entorno:

```bash
cp .env.example .env
```

Luego, completa las variables de entorno necesarias.

📌 Nota: El archivo `.env.example` contiene todas las variables requeridas para la ejecución del sistema, incluyendo credenciales, configuración de servicios y bases de datos.

Ejemplo de algunas variables:

```bash
GITHUB_URL=
GITHUB_USERNAME=
GITHUB_TOCKEN=

CONFIG_SERVER_URL=http://config-server:8888
EUREKA_URL=http://eureka-server:8761/eureka
```

### ▶️ Ejecutar el proyecto

```bash
docker-compose up --build
```

Esto levantará:

- Todos los microservicios
- Bases de datos
- Eureka Server
- API Gateway
- Config Server

---

## 🚧 Estado del proyecto

Actualmente el sistema incluye funcionalidades básicas de:

- **Gestión de productos**
- **Gestión de clientes**
- **Carrito de compras**
- **Registro de ventas**

🔒 Pendiente: Implementación de autenticación y autorización (JWT / OAuth2)

---

## 💡 Decisiones de diseño

- Separación clara de responsabilidades por servicio
- Uso de patrones estándar de Spring Cloud
- Comunicación desacoplada mediante Feign
- Resiliencia mediante Circuit Breaker
- Escalabilidad gracias a arquitectura distribuida

---

## 🎯 Objetivo del proyecto

Este proyecto fue desarrollado con fines educativos y como demostración práctica de conocimientos en:

- Arquitectura de microservicios
- Sistemas distribuidos
- Spring Cloud ecosystem
- Buenas prácticas backend

---

## 📌 Mejoras futuras

- Implementación de autenticación (JWT / OAuth2)
- Observabilidad (logs centralizados, tracing)
- Pruebas automatizadas
- Despliegue en la nube (AWS / GCP)
- CI/CD pipeline

--- 

## 👨‍💻 Autor

Desarrollado por Emanuel Atencia como proyecto de aprendizaje y portafolio profesional.

---

## ⭐ Nota

Este proyecto está enfocado en demostrar conocimiento en arquitectura y no incluye frontend.

---
