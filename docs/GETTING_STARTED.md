# Guía de configuración e inicio

## 1. Prerrequisitos

Instala lo siguiente:

- Node.js 18 o superior
- npm o pnpm
- Git
- acceso a una aplicación registrada en Microsoft Entra ID
- un backend CoffeeHub API operativo

## 2. Clonar el proyecto

```bash
git clone <url-del-repositorio>
cd CoffeeHub-Frontend/frontend
```

## 3. Instalar dependencias

```bash
npm install
```

## 4. Configurar variables de entorno

Crea un archivo `.env` o `.env.local`:

```env
VITE_APP_NAME=CoffeeHub
VITE_API_BASE_URL=http://localhost:8080/api/v1
VITE_AUTH_TENANT_ID=<tenant-id>
VITE_AUTH_CLIENT_ID=<client-id>
VITE_AUTH_AUTHORITY=https://login.microsoftonline.com/<tenant-id>
```

> Las variables públicas deben usarse únicamente para datos no sensibles. Los secretos de autenticación no deben incluirse en el repositorio.

## 5. Registrar Microsoft Entra ID

1. Crear una App Registration para la SPA.
2. Configurar la aplicación para autenticación con MSAL.
3. Definir redirect URIs de desarrollo.
4. Comprobar que el cliente tenga permisos adecuados para el sistema.
5. Verificar que el backend valide correctamente los JWT emitidos por Entra ID.

## 6. Ejecutar el frontend

```bash
npm run dev
```

La aplicación se levanta en el puerto de Vite por defecto, generalmente:

```text
http://localhost:5173
```

## 7. Validar funcionamiento

Verifica lo siguiente:

- La página pública carga sin login.
- La autenticación inicia correctamente.
- El usuario se redirige según su rol.
- Las peticiones a la API incluyen el token.
- Los errores de autenticación o red se muestran de forma clara.

## 8. Build de producción

```bash
npm run build
```

Luego se puede servir el contenido generado en `dist` con un hosting estático.

## 9. Publicación

Se recomienda publicar la aplicación en:

- Vercel
- Netlify
- Azure Static Web Apps
- cualquier hosting que sirva archivos estáticos

## 10. Buenas prácticas

- Mantener configuración separada por entorno.
- No versionar archivos `.env` con información real.
- Revisar logs de navegador para detectar fallas de autenticación.
- Usar rutas protegidas en UI y en backend.
- Mantener la app desacoplada de lógica de dominio del backend.
