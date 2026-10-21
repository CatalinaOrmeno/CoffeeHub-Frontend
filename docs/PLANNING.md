# Planificación del Frontend

## Enfoque

El trabajo del frontend se organiza en entregables incrementales centrados en la experiencia de usuario, la seguridad y la integración con la API. La prioridad es entregar una SPA funcional que soporte navegación por roles y autenticación segura antes de avanzar en refinamientos visuales y despliegue.

## WBS

```mermaid
mindmap
  root((CoffeeHub Frontend))
    1. Definición del producto
      1.1 Usuarios y flujos clave
      1.2 Requisitos de negocio
      1.3 Historias de usuario
    2. Arquitectura de la interfaz
      2.1 React + Vite
      2.2 React Router
      2.3 Estructura de componentes
    3. Autenticación y acceso
      3.1 Microsoft Entra ID
      3.2 MSAL
      3.3 Rutas protegidas
      3.4 Roles y autorización
    4. Integración con API
      4.1 Clientes HTTP
      4.2 Manejo de errores
      4.3 Estados de carga y feedback
    5. UX y diseño
      5.1 Layout base
      5.2 Catálogo y panel de cliente
      5.3 Panel administrativo
    6. Calidad y entrega
      6.1 Tests y validaciones
      6.2 Build de producción
      6.3 Publicación estática
      6.4 Documentación
```

## Cronograma sugerido

```mermaid
gantt
  title CoffeeHub Frontend — hoja de ruta
  dateFormat  YYYY-MM-DD
  axisFormat  %d/%m

  section Fundamentos
  Definición UX y alcance            :w1, 2026-01-05, 7d
  Estructura base del proyecto       :w1b, after w1, 3d

  section Seguridad
  MSAL y Entra ID                   :w2, 2026-01-12, 5d
  Rutas protegidas y roles          :w2b, after w2, 4d

  section Integración
  Servicios API y consumo            :w3, 2026-01-19, 5d
  Manejo de errores y feedback      :w3b, after w3, 4d

  section UX
  Vistas de cliente y admin         :w4, 2026-01-26, 6d
  Diseño y refinamiento visual      :w4b, after w4, 4d

  section Calidad
  Lint, test y build               :w5, 2026-02-02, 5d
  Preparación de despliegue        :w5b, after w5, 4d
```

## Entregables por fase

| Semana | Fase | Actividades | Entregable |
| --- | --- | --- | --- |
| 1 | Alcance y estructura | Definición de arquitectura y UX | SPA base con rutas iniciales |
| 2 | Seguridad | MSAL, Entra ID y autorización | Flujo de autenticación funcional |
| 3 | Integración | Servicios API y manejo de respuestas | App conectada a la API |
| 4 | Experiencia | Diseños para cliente y administración | Interfaz completa |
| 5 | Calidad | Build, pruebas y documentación | Frontend validado |
| 6 | Despliegue | Hosting y configuración | Proyecto listo para publicación |

## Definición de terminado

Una tarea del frontend se considera terminada cuando:

- la funcionalidad se ejecuta correctamente
- la autenticación funciona en entorno real o simulado
- la navegación por roles responde como se espera
- el build de producción pasa
- la documentación refleja el estado actual
- existe validación manual de la experiencia de usuario

## Criterios de calidad

- Los accesos no autorizados deben verse bloqueados en frontend.
- Las rutas públicas deben mantenerse accesibles sin login.
- Los errores de API deben mostrarse sin romper la UX.
- La aplicación debe funcionar con configuración por entorno.
- La documentación debe mantenerse sincronizada con la implementación.