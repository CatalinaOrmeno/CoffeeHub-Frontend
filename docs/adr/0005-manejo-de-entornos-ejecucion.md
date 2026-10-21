# ADR-0005: Configuración por entorno y variables VITE_

- **Estado:** Aceptada
- **Fecha:** 21-10-2026

## Contexto

La SPA necesita diferenciar la configuración entre desarrollo, pruebas y producción. La configuración debe ser segura, reusable y fácil de mantener.

## Decisión

Usar variables de entorno con prefijo `VITE_` para datos públicos necesarios por la aplicación, como la URL de la API, el tenant de Microsoft Entra ID y el client ID. Los archivos `.env` o `.env.local` se usan solo para entornos locales y nunca se versionan con secretos reales.

## Alternativas descartadas

- hardcode de URLs y client IDs dentro del código fuente: poco portable y riesgoso
- almacenamiento de secretos en archivos versionados: no es seguro
- mantener una sola configuración para todos los entornos: aumenta errores al desplegar

## Consecuencias

La aplicación es más portable y estable entre entornos. La disciplina de configuración es necesaria para evitar errores de autenticación o integración con la API.
