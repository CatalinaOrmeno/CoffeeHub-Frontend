# ADR-0004: Despliegue de frontend estático

- **Estado:** Aceptada
- **Fecha:** 21-10-2026

## Contexto

La aplicación debe ofrecer una experiencia moderna con tiempos de carga rápidos, mantenimiento simple y despliegue fácil en entornos cloud.

## Decisión

Publicar la SPA como frontend estático usando Vite y un hosting compatible con sitios estáticos, como Vercel, Netlify o Azure Static Web Apps. La interfaz se sirve desde el directorio `dist` generado por el build de producción.

## Alternativas descartadas

- correr el frontend en un servidor Node/Express para producción: aumenta la operación y no aporta valor al alcance actual
- hosting ad-hoc con despliegue manual sin pipeline: genera más riesgo y menos repetibilidad
- despliegue monolítico con backend y frontend juntos: complica la separación de módulos

## Consecuencias

El frontend queda más ligero y fácil de escalar, con despliegues rápidos y menos dependencias de runtime. La configuración del entorno debe gestionarse con variables `VITE_*` para cada entorno.