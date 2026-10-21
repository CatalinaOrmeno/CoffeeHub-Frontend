# ADR-0001: Microsoft Entra ID y MSAL

- **Estado:** Aceptada
- **Fecha:** 21-10-2026

## Contexto

La aplicación necesita autenticar usuarios y diferenciar accesos según el tipo de persona: público, cliente y administrador. La autenticación debe ser segura y compatible con la API del backend.

## Decisión

Usar Microsoft Entra ID como proveedor de identidad y `@azure/msal-react` / `@azure/msal-browser` para gestionar el flujo de login en la SPA. La aplicación añade el token Bearer en cada llamada autenticada a la API de CoffeeHub.

## Alternativas descartadas

- Auth0 y Keycloak: válidos, pero añaden más complejidad operativa para el alcance actual.
- autenticación local sin proveedor externo: no escala ni se alinea con la identidad empresarial del caso de uso.
- una solución manual con almacenamiento de credenciales locales: insegura y poco mantenible.

## Consecuencias

Se obtiene una experiencia de acceso segura, compatible con roles y fácil de desplegar en cloud. El frontend queda dependiente de la configuración correcta del tenant y de la validación de claims en backend.