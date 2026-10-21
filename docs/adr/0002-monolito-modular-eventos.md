# ADR-0002: Frontend SPA con React y Vite

- **Estado:** Aceptada
- **Fecha:** 21-10-2026

## Contexto

La interfaz necesita resolver distintos flujos de usuario con una experiencia moderna y reusable, sin duplicar aplicaciones ni crear una arquitectura pesada.

## Decisión

Construir una SPA React con Vite, Tailwind CSS y React Router. La navegación se organiza en rutas públicas, de cliente y administrativas. La capa de UI se comunica con la API mediante servicios y hooks reutilizables.

## Alternativas descartadas

- Una app monolítica renderizada por servidor: menos fluida y menos adecuada para experiencias dinámicas.
- Next.js para un alcance SPA simple: agrega complejidad innecesaria.
- Frameworks alternativos sin ecosistema fuerte para este caso: reducen velocidad de desarrollo.

## Consecuencias

Obtendremos una SPA rápida, moderna y desplegable como sitio estático. La principal carga operativa será la coordinación con la API de backend, rutas protegidas y la configuración de entorno.