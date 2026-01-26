# 🏢 Guía: Recrear Servicios en Cuenta de Empresa

Esta guía te ayudará a recrear los servicios de Psicologa en la cuenta de la empresa para que tengan control total sobre pagos y configuración.

---

## 📋 Checklist Pre-Deploy

- [ ] Tienes acceso a la cuenta de la empresa en Render
- [ ] El repositorio de GitHub está conectado o listo para conectar
- [ ] Tienes la URL del nuevo backend (se generará después del deploy)
- [ ] Tienes acceso para actualizar el código en GitHub

---

## 🔧 Paso 1: Crear el Backend en la Cuenta de la Empresa

### 1.1 Acceder a la cuenta de la empresa
1. Inicia sesión en Render con el email de la empresa
2. Ve al Dashboard

### 1.2 Crear el servicio Web (Backend)
1. Click en **"+ New"** → **"Web Service"**
2. Conecta tu repositorio de GitHub (o crea uno nuevo si no está conectado)
3. Selecciona el repositorio que contiene tu proyecto

### 1.3 Configuración del Backend
Configura estos valores:

- **Name**: `psicologa-backend`
- **Environment**: `Node`
- **Region**: `Virginia` (o la que prefieras)
- **Branch**: `main` (o `master`, según tu repo)
- **Root Directory**: (dejar vacío, el código está en la raíz)
- **Build Command**: `cd backend && npm install`
- **Start Command**: `cd backend && node server.js`
- **Plan**: `Free` (por ahora) - ⚠️ **NOTA**: Puedes empezar con Free y actualizar a Starter después. El plan Free se duerme después de 15 minutos de inactividad y NO soporta disco persistente.

### 1.4 Variables de Entorno
En la sección **"Environment"**, agrega:
- `NODE_ENV`: `production`
- `PORT`: `4000` (opcional, Render lo asigna automáticamente)

### 1.5 Crear el Disco Persistente (Solo con Plan Starter)
⚠️ **IMPORTANTE**: El disco persistente solo está disponible con el plan Starter o superior.

**Si estás usando el plan Free por ahora:**
- ⚠️ Los datos se pueden perder cuando el servicio se reinicie o se duerma
- Puedes actualizar a Starter más tarde para habilitar el disco persistente

**Si ya tienes el plan Starter:**
1. Una vez creado el servicio, ve a la pestaña **"Disk"**
2. Click en **"Create Disk"**
3. Configuración:
   - **Name**: `database-disk`
   - **Mount Path**: `/data`
   - **Size**: `1 GB` (suficiente para SQLite)
4. Click en **"Create"**

5. Configurar Variable de Entorno para el Disco:
   - Ve a **"Environment"** del servicio
   - Agrega:
     - **Key**: `DATABASE_PATH`
     - **Value**: `/data`
   - Guarda los cambios

### 1.7 Esperar el Deploy
- Render comenzará a construir y desplegar
- Esto puede tomar 5-10 minutos
- **IMPORTANTE**: Copia la URL que se genera (ej: `https://psicologa-backend-xxxx.onrender.com`)
- **Guarda esta URL**, la necesitarás en el Paso 3

---

## 🎨 Paso 2: Crear el Frontend en la Cuenta de la Empresa

### 2.1 Crear el servicio Static Site
1. En el Dashboard, click en **"+ New"** → **"Static Site"**
2. Conecta el mismo repositorio de GitHub

### 2.2 Configuración del Frontend
- **Name**: `psicologa-system` (o `psicologa-frontend`)
- **Branch**: `main` (o `master`)
- **Root Directory**: (dejar vacío)
- **Build Command**: `echo "No build needed"`
- **Publish Directory**: `.` (punto, significa la raíz)

### 2.3 Crear el Static Site
- Click en **"Create Static Site"**
- Espera el deploy (2-3 minutos)
- Copia la URL del frontend (ej: `https://psicologa-system-xxxx.onrender.com`)

---

## 🔄 Paso 3: Actualizar la URL del Backend en el Código

### 3.1 Actualizar app.js
1. Abre `app.js` en tu editor
2. Busca la línea 13 que dice:
   ```javascript
   : "https://psicologa-backend.onrender.com/api";
   ```
3. Reemplázala con la nueva URL del backend (la que copiaste en el Paso 1.7):
   ```javascript
   : "https://psicologa-backend-xxxx.onrender.com/api";
   ```
   (Reemplaza `xxxx` con el ID real de tu nuevo servicio)

### 3.2 Subir el cambio a GitHub
**Con GitHub Desktop:**
1. Verás el cambio en "Changes"
2. Escribe un mensaje: "Actualizar URL del backend a cuenta de empresa"
3. Click en "Commit to main"
4. Click en "Push origin"

**Con Git:**
```bash
git add app.js
git commit -m "Actualizar URL del backend a cuenta de empresa"
git push
```

### 3.3 Esperar Auto-Deploy
- Render detectará el cambio automáticamente
- El frontend se actualizará con la nueva URL (2-3 minutos)

---

## ✅ Paso 4: Verificar que Todo Funciona

### 4.1 Verificar Backend
1. Abre la URL del backend en el navegador
2. Deberías ver algo como: `{"message":"API funcionando"}` o un error 404 (normal, la API está en `/api`)
3. Prueba: `https://tu-backend-url.onrender.com/api/appointments` (debería responder)

### 4.2 Verificar Frontend
1. Abre la URL del frontend
2. La aplicación debería cargar correctamente
3. Intenta iniciar sesión
4. Verifica que puedas ver el calendario y agendar citas

### 4.3 Verificar Base de Datos
1. Crea una cita de prueba desde el frontend
2. Verifica que se guarde correctamente
3. Si tienes acceso al admin, verifica que aparezca en el panel

---

## 🗑️ Paso 5: (Opcional) Eliminar Servicios Antiguos

**⚠️ IMPORTANTE**: Solo haz esto después de verificar que todo funciona en la cuenta nueva.

1. En tu cuenta personal (alejandrolopeztascon11c@gmail.com)
2. Ve a cada servicio antiguo
3. Click en **"Settings"** → **"Delete Service"**
4. Confirma la eliminación

---

## 📝 Notas Importantes

### Plan Free (Actual)
- ⚠️ **Se duerme después de 15 minutos de inactividad** - La primera petición después de dormirse puede tardar 30-60 segundos
- ⚠️ **NO soporta disco persistente** - Los datos pueden perderse cuando el servicio se reinicia
- ✅ **Gratis** - Perfecto para pruebas y desarrollo

### Plan Starter (Recomendado para Producción)
- ✅ **Servidor siempre activo** - No se duerme
- ✅ **Soporta disco persistente** - Los datos se guardan permanentemente
- ✅ **$7/mes** - Costo razonable para producción

### Actualizar de Free a Starter
1. Ve a tu servicio en Render
2. Click en **"Settings"** → **"Plan"** (o busca "Instance Type")
3. Selecciona **"Starter"**
4. Guarda los cambios
5. Luego puedes crear el disco persistente (ver Paso 1.5)

### Otras Notas
- **Auto-Deploy**: Render actualizará automáticamente cuando hagas `git push`
- **URLs**: Las URLs no cambian después del primer deploy, así que puedes generar el QR una vez que todo esté funcionando

---

## 🆘 Si Algo Sale Mal

1. **El backend no inicia:**
   - Revisa los logs en Render (pestaña "Logs")
   - Verifica que el "Start Command" sea correcto: `cd backend && node server.js`
   - Verifica que las variables de entorno estén configuradas

2. **El frontend no se conecta al backend:**
   - Verifica que la URL en `app.js` sea correcta
   - Verifica que el backend esté desplegado y funcionando
   - Revisa la consola del navegador (F12) para ver errores

3. **Los datos no se guardan:**
   - Verifica que el disco persistente esté creado
   - Verifica que la variable `DATABASE_PATH` esté configurada
   - Verifica que el backend esté usando el disco (revisa los logs)

---

## ✅ Checklist Final

- [ ] Backend creado y desplegado en cuenta de empresa
- [ ] Disco persistente configurado
- [ ] Frontend creado y desplegado
- [ ] URL del backend actualizada en `app.js`
- [ ] Cambio subido a GitHub
- [ ] Frontend actualizado automáticamente
- [ ] Todo funciona correctamente
- [ ] Servicios antiguos eliminados (opcional)

---

¡Listo! La empresa ahora tiene control total sobre los servicios y pagos. 🎉
