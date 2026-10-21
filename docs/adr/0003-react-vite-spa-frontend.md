# ADR-0003: Rutas protegidas y autorización por rol

- **Estado:** Aceptada
- **Fecha:** 21-10-2026

## Contexto

La interfaz presenta distintos tipos de usuarios con permisos diferentes. Se requiere separar la experiencia pública, la de cliente y la administrativa sin dejar huecos de seguridad.

## Decisión

Implementar rutas protegidas con React Router y controlar la visibilidad según el rol del usuario. La SPA define accesos para `/`, `/portal/*` y `/admin/*`, usando la información del token para decidir qué se muestra al usuario.

## Alternativas descartadas

- Mostrar toda la UI a todos los usuarios: rompe la separación de permisos.
- Restringir solo por ocultación visual: no es suficiente, porque la autorización debe reforzarse en backend.
- Múltiples clientes separados para cada rol: aumenta la complejidad y la duplicación de código.

## Consecuencias

La experiencia es más segura y clara para cada tipo de usuario. El frontend debe coordinar la autenticación con la API y los permisos reales que validan los endpoints protegidos.