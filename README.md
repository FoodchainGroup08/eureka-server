# eureka-server

Netflix **Eureka** service registry for FoodChain. Microservices and the API Gateway register here so routing uses logical service names (`order-service`, `menu-service`, …) instead of fixed hosts.

## Port

**8761** — Eureka dashboard and REST API: `http://localhost:8761`

## Configuration

Typically pulls defaults from **Spring Cloud Config** (`optional:configserver:http://localhost:8888`). Other services set:

```yaml
eureka:
  client:
    service-url:
      defaultZone: http://localhost:8761/eureka/
```

## Running

```bash
./mvnw spring-boot:run
```

Or via **foodchain-deployment** Docker Compose (`depends_on` config-server in the stack).
