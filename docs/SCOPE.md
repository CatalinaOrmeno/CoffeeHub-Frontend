# Declaración de Alcance — CoffeeHub Frontend

## Propósito

CoffeeHub Frontend es el módulo responsable de la experiencia web del producto CoffeeHub. Su objetivo es ofrecer una interfaz moderna, segura y accesible para usuarios públicos, clientes y administradores, consumiendo la API REST del backend.

## Objetivos

1. Presentar la identidad visual del producto.
2. Permitir navegación pública y rutas protegidas.
3. Implementar flujo de autenticación con Microsoft Entra ID.
4. Consumir endpoints del backend con autorización adecuada.
5. Exponer una experiencia diferenciada para cliente y administración.
6. Mantener la aplicación desplegable como frontend estático.

## Incluido

- Portal público con información general del producto.
- Catálogo consultable desde la UI.
- Portal de cliente con autenticación por roles.
- Portal administrativo con gestión operativa.
- Manejo de sesión y tokens mediante MSAL.
- Rutas protegidas por rol.
- Consumo de API REST con encabezado Bearer.
- Configuración por variables de entorno.
- Diseño responsive y experiencia de usuario clara.
- Despliegue estático en un host compatible con Vite.

## Fuera de alcance

- Lógica de negocio del backend.
- Base de datos relacional o documental.
- Procesamiento de pagos reales.
- Gestión de inventario, suscripciones o eventos internos del dominio backend.
- Servicios de mensajería o integración de infraestructura de datos.
- Desarrollo de API o microservicios.
- Implementación de autenticación custom sin Microsoft Entra ID.

## Restricciones y supuestos

- La SPA depende de un backend CoffeeHub API disponible.
- La autenticación se realiza mediante Microsoft Entra ID.
- La UI debe respetar los roles `ROLE_CLIENT` y `ROLE_ADMIN`.
- Las rutas públicas, de cliente y admin se controlan desde la SPA.
- La información sensible no debe exponerse en el frontend.
- La configuración pública se maneja mediante `VITE_*`.

## Criterios de aceptación

| ID | Criterio verificable |
| --- | --- |
| AC-01 | La SPA carga correctamente en entorno local con `npm run dev`. |
| AC-02 | El usuario público puede navegar por la vista general sin autenticación. |
| AC-03 | El usuario con `ROLE_CLIENT` accede al portal de cliente y no al panel administrativo. |
| AC-04 | El usuario con `ROLE_ADMIN` accede al panel administrativo y no al portal del cliente. |
| AC-05 | La aplicación obtiene tokens desde Microsoft Entra ID y los envía al backend. |
| AC-06 | La UI consume la API correctamente mediante variables de entorno de configuración. |
| AC-07 | La documentación del módulo compila con MkDocs sin errores. |
| AC-08 | La aplicación puede desplegarse como frontend estático sin depender de un runtime Java. |

## Entregables

- Código fuente de la SPA React/Vite.
- Configuración de entorno para desarrollo.
- Documentación técnica del frontend.
- Definición de rutas, roles y consumo de API.
- Estrategia de despliegue en hosting estático.