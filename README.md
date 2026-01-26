# 🧠 Aplicación de Gestión de Citas Psicológicas

Sistema web para la gestión de citas con psicóloga - Círculo de Apoyo

## 📋 Características

- ✅ Sistema de autenticación (pacientes y administrador)
- ✅ Calendario interactivo para agendar citas
- ✅ Gestión de horarios disponibles
- ✅ Notificaciones en tiempo real
- ✅ Panel de administración
- ✅ Aplicación Web Progresiva (PWA) - Instalable en dispositivos móviles

## 🛠️ Tecnologías

- **Frontend**: HTML, CSS, JavaScript (Vanilla)
- **Backend**: Node.js + Express
- **Base de Datos**: SQLite
- **Hosting**: Render.com

## 🚀 Instalación Local

### Requisitos
- Node.js (v18 o superior)
- npm

### Pasos

1. Clonar el repositorio:
```bash
git clone https://github.com/aprendizcoobup/psicologa-app.git
cd psicologa-app
```

2. Instalar dependencias del backend:
```bash
cd backend
npm install
```

3. Iniciar el servidor:
```bash
node server.js
```

4. Abrir el frontend:
- Abre `index.html` en tu navegador
- O usa un servidor local (ej: `python -m http.server 8000`)

## 📱 Uso

### Para Pacientes
1. Registrarse o iniciar sesión
2. Seleccionar fecha disponible en el calendario
3. Seleccionar horario
4. Confirmar cita

### Para Administrador
- Usuario: `admin`
- Contraseña: (ver configuración en backend/db.js)

## 🌐 Despliegue

Ver `README-DEPLOY.md` para instrucciones de despliegue en Render.

## 📝 Licencia

Uso interno - Cooperativa Urbanos Pereira
