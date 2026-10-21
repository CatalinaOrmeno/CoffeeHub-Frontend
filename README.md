# CoffeeHub Frontend

SPA en React + Vite para la experiencia web de CoffeeHub. Este módulo se encarga de presentar el catálogo, la autenticación de usuarios, los flujos de suscripción y la administración del cliente, consumiendo la API REST del backend de CoffeeHub.

## Propósito

El frontend actúa como capa de experiencia de usuario para:

- Portal público con información del club y catálogo.
- Portal de cliente con planes, suscripciones y estado de cuenta.
- Consola administrativa para gestión operativa.
- Inicio de sesión con Microsoft Entra ID y validación de roles.
- Consumo seguro de la API mediante JWT Bearer.

## Objetivos del módulo

1. Exponer una SPA moderna y rápida con React + Vite.
2. Gestionar autenticación con Microsoft Entra ID usando MSAL.
3. Separar rutas públicas, cliente y administrativa.
4. Consumir la API REST de CoffeeHub con autorización por roles.
5. Desplegarse como aplicación estática en un hosting moderno.

## Arquitectura de la interfaz

La aplicación se compone de:

- `React + Vite` como base de la interfaz
- `React Router` para navegación
- `@azure/msal-react` y `@azure/msal-browser` para autenticación
- `Axios` o fetch nativo para consumo de API
- `Tailwind CSS` o un kit de UI (PrimeReact, Mantine, Shadcn) para diseño
- variables `VITE_*` para configuración pública

## Rutas esperadas

- `/` — portal público
- `/portal/*` — flujo de cliente autenticado
- `/admin/*` — flujo administrativo autenticado

## Autenticación

El frontend obtiene un token desde Microsoft Entra ID usando PKCE y lo incluye en las llamadas a la API con el encabezado:

```http
Authorization: Bearer <token>
```

La autorización se valida por roles del usuario, por ejemplo:

- `ROLE_CLIENT`
- `ROLE_ADMIN`

## Stack técnico

- React 18+
- Vite
- TypeScript
- React Router
- MSAL para Microsoft Entra ID
- CSS moderno con Tailwind o UI kit
- Node.js y npm para desarrollo local

## Requisitos

- Node.js 18 o superior
- npm o pnpm
- acceso a una aplicación registrada en Microsoft Entra ID
- un backend CoffeeHub API disponible en entorno local o remoto

## Inicio rápido

```bash
npm install
npm run dev
```

## Variables de entorno

Crear un archivo `.env` con valores públicos del cliente:

```env
VITE_APP_NAME=CoffeeHub
VITE_API_BASE_URL=http://localhost:8080/api/v1
VITE_AUTH_TENANT_ID=<tenant-id>
VITE_AUTH_CLIENT_ID=<client-id>
VITE_AUTH_AUTHORITY=https://login.microsoftonline.com/<tenant-id>
```

> No se deben incluir secretos del cliente ni credenciales privadas en el repositorio.

## Scripts disponibles

```bash
npm run dev
npm run build
npm run preview
npm run lint
```

## Estructura sugerida

```text
frontend/
├── public/
├── src/
│   ├── app/
│   ├── components/
│   ├── features/
│   ├── hooks/
│   ├── routes/
│   ├── services/
│   ├── styles/
│   ├── utils/
│   ├── App.tsx
│   ├── main.tsx
│   └── index.css
├── .env.example
├── package.json
├── vite.config.ts
├── tsconfig.json
├── index.html
└── README.md
```

## Despliegue

La aplicación se despliega como frontend estático, por ejemplo:

- Vercel
- Netlify
- Azure Static Web Apps
- cualquier hosting estático compatible con Vite

## Relación con el backend

Este repositorio no implementa la lógica de negocio ni bases de datos. Su responsabilidad es:

- presentar la interfaz
- autenticar usuarios
- orquestar navegación
- consumir endpoints del backend CoffeeHub API
- reflejar el estado del sistema en la experiencia del usuario

## Documentación

- `docs/SCOPE.md`
- `docs/PLANNING.md`
- `docs/INFRASTRUCTURE.md`
- `docs/GETTING_STARTED.md`