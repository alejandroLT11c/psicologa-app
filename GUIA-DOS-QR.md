# 📱 Guía: Sistema de Dos QR

La aplicación ahora funciona con **dos códigos QR diferentes** para usuarios y administradores.

---

## 🔵 QR de Usuario (Público)

### URL
```
https://tu-frontend-url.onrender.com
```
(Sin parámetros adicionales)

### Características
- ✅ **Sin login**: Los usuarios acceden directamente a la vista principal
- ✅ **Sin mostrar usuario**: No aparece ningún nombre en la parte superior derecha
- ✅ **Identificación por dispositivo**: Cada dispositivo tiene un ID único guardado en `localStorage`
- ✅ **Agendar citas**: Al agendar, se pide:
  - Nombre completo
  - Número de celular
- ✅ **Ver solo sus citas**: Cada dispositivo solo ve las citas que él mismo agendó
- ✅ **Horarios ocupados**: Si otro usuario tomó un horario, aparece como "no disponible" (gris)

### Flujo de Usuario
1. Usuario escanea el QR
2. Se carga directamente la página (sin login)
3. Ve el calendario con días disponibles
4. Selecciona un día y horario
5. Completa nombre y teléfono
6. Confirma la cita
7. Ve solo sus propias citas en "Mis citas"

---

## 🔴 QR de Administrador

### URL
```
https://tu-frontend-url.onrender.com?admin=true
```
(Con el parámetro `?admin=true`)

### Características
- 🔐 **Requiere login**: Muestra formulario de inicio de sesión
- 👤 **Login simplificado**: Solo pide:
  - Usuario (nombre del admin)
  - Contraseña (número de identificación o contraseña configurada)
- ❌ **Sin términos**: No se muestra el checkbox de términos y condiciones
- 📊 **Vista completa**: Puede ver todas las citas de todos los usuarios
- ✏️ **Gestión**: Puede confirmar, rechazar, deshabilitar días/horas

### Flujo de Administrador
1. Administrador escanea el QR
2. Ve el formulario de login
3. Ingresa usuario y contraseña
4. Accede al panel de administración
5. Ve todas las citas con nombres y teléfonos de los pacientes
6. Puede gestionar días, horas y citas

---

## 🔧 Configuración Técnica

### Backend
- ✅ Tabla `appointments` modificada para tener `device_id`, `patient_name`, `patient_phone`
- ✅ Endpoint `/api/auth/admin-login` para login simplificado de admin
- ✅ Endpoint `/api/appointments` acepta `deviceId`, `patientName`, `patientPhone` para usuarios anónimos
- ✅ Endpoint `/api/appointments-by-device` para obtener citas por dispositivo

### Frontend
- ✅ Detección de modo: `?admin=true` en la URL
- ✅ `deviceId` generado automáticamente y guardado en `localStorage`
- ✅ Modal de agendar cita pide nombre y teléfono en modo usuario
- ✅ Login admin simplificado (solo usuario/contraseña)
- ✅ Usuario oculto en header para modo usuario

---

## 📋 Generar los QR

### QR de Usuario
```
URL: https://tu-frontend-url.onrender.com
```
Usa cualquier generador de QR (como https://www.qr-code-generator.com/) y genera el código con esta URL.

### QR de Administrador
```
URL: https://tu-frontend-url.onrender.com?admin=true
```
Genera otro QR con esta URL (incluyendo el parámetro `?admin=true`).

---

## 🎯 Ventajas del Nuevo Sistema

1. **Más simple para usuarios**: No necesitan registrarse ni recordar credenciales
2. **Privacidad**: Cada dispositivo solo ve sus propias citas
3. **Flexibilidad**: Los usuarios pueden usar cualquier dispositivo
4. **Información completa**: La administradora siempre tiene nombre y teléfono del paciente
5. **Seguridad**: Solo los administradores pueden acceder al panel con login

---

## ⚠️ Notas Importantes

- El `deviceId` se genera automáticamente la primera vez que se accede desde un dispositivo
- Si un usuario borra el `localStorage` del navegador, se generará un nuevo `deviceId` y no verá sus citas anteriores
- Los horarios ocupados por otros usuarios aparecen como "no disponibles" en modo usuario
- La administradora siempre ve todas las citas con la información completa (nombre y teléfono)

---

¡Listo! Ahora tienes dos QR diferentes para usuarios y administradores. 🎉
