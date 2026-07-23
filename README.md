# 🚪 Banking Gateway

API Gateway del sistema bancario. Es el **punto de entrada único** para todas las peticiones externas. Basado en **Spring Cloud Gateway**, se encarga de enrutar, autenticar y balancear el tráfico hacia los microservicios.

## 📌 ¿Qué hace este servicio?

```
Cliente (Postman / App)
        │
        ▼
  🚪 API Gateway         ← estás aquí
  ├── Valida JWT con Keycloak
  ├── Enruta hacia el servicio correcto
  └── Balancea la carga
        │
        ├──▶ user-service        :8081
        ├──▶ account-service     :8082
        ├──▶ transaction-service :8083
        └──▶ notification-service:8084
```

## 🛠️ Stack tecnológico

| Tecnología | Versión | Uso |
|---|---|---|
| Java | 21 (LTS) | Lenguaje principal |
| Spring Boot | 3.x | Framework base |
| Spring Cloud Gateway | 4.x | Enrutamiento y filtros |
| Spring Security | 6.x | Validación de tokens JWT |
| Maven | 3.x | Gestión de dependencias |

## ▶️ Puerto

| Entorno | Puerto |
|---|---|
| Local | 8080 |

> ⚠️ Asegúrate de que la infraestructura esté corriendo antes de levantar este servicio. Ver [banking-infrastructure](https://github.com/TU_USUARIO/banking-infrastructure).

## 🚀 Correr el servicio

```bash
# Clonar el repositorio
git clone https://github.com/TU_USUARIO/banking-gateway
cd banking-gateway

# Compilar
mvn clean install

# Correr
mvn spring-boot:run
```

## 📁 Estructura del proyecto

```
banking-gateway/
├── src/
│   └── main/
│       ├── java/
│       │   └── com/banking/gateway/
│       │       └── GatewayApplication.java
│       └── resources/
│           └── application.yml
└── pom.xml
```

## 🔀 Rutas configuradas

| Ruta | Microservicio destino |
|---|---|
| `/api/users/**` | user-service |
| `/api/accounts/**` | account-service |
| `/api/transactions/**` | transaction-service |
| `/api/notifications/**` | notification-service |

## 🗂️ Repositorios relacionados

- [banking-infrastructure](https://github.com/TU_USUARIO/banking-infrastructure)
- [banking-config-server](https://github.com/TU_USUARIO/banking-config-server)
- [banking-user-service](https://github.com/TU_USUARIO/banking-user-service)
- [banking-account-service](https://github.com/TU_USUARIO/banking-account-service)
- [banking-transaction-service](https://github.com/TU_USUARIO/banking-transaction-service)
- [banking-notification-service](https://github.com/TU_USUARIO/banking-notification-service)
