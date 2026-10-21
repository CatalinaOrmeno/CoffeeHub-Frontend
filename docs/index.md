# CoffeeHub Frontend

Este módulo representa la capa de experiencia de usuario de CoffeeHub. La aplicación está construida en React + Vite y está orientada a entregar una experiencia moderna para clientes, visitantes y administradores, consumiendo la API REST del backend de CoffeeHub.

## Propósito del módulo

La SPA de CoffeeHub tiene como objetivo:

- presentar el catálogo y la propuesta de valor del club de café
- autenticar a usuarios con Microsoft Entra ID
- diferenciar acceso público, cliente y administrativo
- consumir servicios del backend con autorización por roles
- desplegarse de forma eficiente como aplicación estática

## Usuarios y flujos

- `Público`: consulta información general y catálogo.
- `Cliente`: inicia sesión y gestiona su relación con CoffeeHub.
- `Administrador`: accede a funcionalidades operativas y administrativas.

## Capas principales

- `UI`: componentes, layouts, formularios y navegación
- `Routing`: rutas públicas y protegidas con React Router
- `Auth`: Microsoft Entra ID + MSAL
- `API Client`: consumo seguro de endpoints del backend
- `Deployment`: build de producción y publicación estática

## Rutas de navegación

- `/` — portal público
- `/portal/*` — zona del cliente
- `/admin/*` — zona de administración

## Tecnologías clave

- React
- Vite
- TypeScript
- React Router
- MSAL
- Tailwind CSS o UI kit compatible

## Relación con el backend

El frontend no define la lógica de negocio ni la persistencia. Su responsabilidad es orquestar la experiencia del usuario, autenticar con tokens y consumir la API del backend de forma segura y transparente.

## Documentación disponible

- [Alcance del módulo](SCOPE.md)
- [Planificación](PLANNING.md)
- [Arquitectura e infraestructura](INFRASTRUCTURE.md)
- [Guía de configuración](GETTING_STARTED.md)
- [Registros de decisión (ADR)](adr/)