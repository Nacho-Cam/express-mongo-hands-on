# Despliegue de la lista en Render y MongoDB Atlas

## 1. Crear tu fork

1. Abre <https://github.com/fjbanezares/express-mongo-hands-on> e inicia sesión en GitHub.
2. Pulsa **Fork** y después **Create fork** para crear una copia en tu cuenta.
3. Clona la URL de tu fork en tu ordenador y copia estos cambios a esa copia (o aplícalos allí).
4. Personaliza `DISPLAY_NAME` con tu nombre en el entorno de Render.

## 2. Preparar MongoDB Atlas

1. Crea un clúster y un usuario de base de datos en MongoDB Atlas.
2. En **Network Access**, agrega `0.0.0.0/0` para permitir conexiones desde las IP dinámicas de Render, como pide la práctica.
3. Copia la cadena de conexión de la aplicación y reemplaza el usuario, la contraseña y el nombre de base de datos. Codifica los caracteres especiales de la contraseña para una URI.
4. Atlas protege el acceso de red con la lista permitida, pero `0.0.0.0/0` admite conexiones desde cualquier dirección. Úsalo solo para esta práctica y elimínalo o restringe el acceso al terminar.

## 3. Crear el servicio web de Render

1. En Render, crea un **New Web Service** y conecta el fork de GitHub.
2. Selecciona la rama `main`.
3. Configura **Build Command** como `npm install` y **Start Command** como `npm start`.
4. En **Environment**, agrega `MONGODB_URI` con la URI de Atlas y `DISPLAY_NAME` con tu nombre. No guardes la URI real en Git.
5. Despliega y espera a que los logs indiquen que MongoDB está conectado.
6. Abre la URL `https://...onrender.com` desde el ordenador y el móvil.

## Ejecución local

Define `MONGODB_URI` en el entorno de tu terminal antes de ejecutar `npm start`; `.env.example` solo sirve como plantilla y no se carga automáticamente. En PowerShell puedes usar `$env:MONGODB_URI = "<tu-uri-de-atlas>"` y `$env:DISPLAY_NAME = "<tu-nombre>"`. Ejecuta `npm install` y `npm start`. No subas la URI real a Git.

## Entregables de la práctica

- URL pública del servicio de Render.
- Capturas de la aplicación y de la prueba desde el móvil.
- Vídeo de un minuto mostrando la aplicación desplegada y el selector de listas.
