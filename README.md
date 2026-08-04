# Docker Multi-Stage Builds en una API NestJS GraphQL

<p align="center">
  <img src="https://www.docker.com/wp-content/uploads/2022/03/Moby-logo.png" alt="Docker" width="220" />
</p>

## Descripción

Este repositorio se usa como ejercicio para practicar Docker sobre una API GraphQL hecha con NestJS que ya existía en el proyecto. El foco principal fue trabajar la imagen con un `Dockerfile` multi-stage y usar el código base como práctica de contenedores.

El objetivo del ejercicio es mostrar cómo organizar una imagen de Docker más limpia y mantener los comandos útiles para desarrollo, pruebas y ejecución.

## Lo que hice en este proyecto

* Creé el `Dockerfile` para practicar Docker multi-stage.
* Usé el código NestJS GraphQL que ya estaba en el proyecto como base para probar la construcción y ejecución de la imagen.
* Conservé los comandos útiles para levantar, probar y validar la aplicación.

## Estructura general

* `src/app.module.ts`: configuración principal de GraphQL y módulos de la aplicación.
* `src/todo/todo.resolver.ts`: queries, mutations y agregaciones del ejemplo.
* `src/todo/todo.service.ts`: lógica en memoria para los todos del ejercicio.
* `Dockerfile`: construcción multi-stage de la imagen.

## Comandos útiles

### Instalar dependencias

```bash
npm install
```

### Ejecutar la aplicación

```bash
# desarrollo
npm run start

# modo observador
npm run start:dev

# depuración
npm run start:debug

# producción
npm run start:prod
```

### Compilar y validar

```bash
npm run build
npm run lint
```

### Pruebas

```bash
# pruebas unitarias
npm run test

# pruebas en modo watch
npm run test:watch

# cobertura
npm run test:cov

# pruebas e2e
npm run test:e2e
```

### Formateo

```bash
npm run format
```

## Docker

### Construir la imagen

```bash
docker build -t tu_usuario/graphql-actions:latest .
```

### Construcción multi-plataforma con Buildx

```bash
docker buildx build --platform linux/amd64,linux/arm64 -t tu_usuario/graphql-actions:latest .
```

### Ejecutar el contenedor

```bash
docker run --name graphql-actions -p 3000:3000 tu_usuario/graphql-actions:latest
```

### Ver historial de capas

```bash
docker history tu_usuario/graphql-actions:latest
```

## Nota

El esquema GraphQL se genera automáticamente en `src/schema.gql`, así que conviene volver a compilar la aplicación después de hacer cambios en resolvers, inputs o entidades.

---

*Proyecto de práctica enfocado en Docker, usando una API NestJS GraphQL como base de prueba.*
