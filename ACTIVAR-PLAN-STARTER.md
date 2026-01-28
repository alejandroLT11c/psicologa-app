# 🚀 Activar Plan Starter y Configurar Disco Persistente

Ya tienes la tarjeta agregada. Ahora sigue estos pasos para activar el plan Starter y configurar el disco persistente.

---

## ✅ Paso 1: Actualizar el Servicio a Plan Starter

1. Ve a tu servicio **"psicologa-backend"** en Render
2. En el menú izquierdo, haz clic en **"Settings"**
3. Busca la sección **"Plan"** o **"Instance Type"**
4. Cambia de **"Free"** a **"Starter"**
5. Haz clic en **"Save Changes"** o **"Update Plan"**
6. ⚠️ **Render te pedirá confirmar el pago** - Confirma (será $7/mes)

**Espera 1-2 minutos** mientras Render actualiza el servicio.

---

## 💾 Paso 2: Crear el Disco Persistente

Una vez que el servicio esté en plan Starter:

1. En el menú izquierdo del servicio, haz clic en **"Disk"**
2. Haz clic en **"Create Disk"** o **"Add Disk"**
3. Configuración:
   - **Name**: `database-disk`
   - **Mount Path**: `/data`
   - **Size**: `1 GB` (suficiente para SQLite, puedes aumentar después)
4. Haz clic en **"Create"**

**Espera 1-2 minutos** mientras Render crea el disco.

---

## 🔧 Paso 3: Configurar la Variable de Entorno

1. En el menú izquierdo, haz clic en **"Environment"**
2. Haz clic en **"Add Environment Variable"**
3. Agrega:
   - **Key**: `DATABASE_PATH`
   - **Value**: `/data` (debe ser igual al Mount Path del disco)
4. Haz clic en **"Save Changes"**

---

## 🔄 Paso 4: Reiniciar el Servicio

Para que los cambios surtan efecto:

1. Ve a la pestaña **"Events"** o **"Manual Deploy"**
2. Haz clic en **"Manual Deploy"** → **"Deploy latest commit"**
3. Espera a que termine el despliegue (2-5 minutos)

---

## ✅ Paso 5: Verificar que Funciona

1. Después del despliegue, ve a tu aplicación
2. Crea una cita de prueba
3. Ve a Render → **"Manual Deploy"** → despliega de nuevo
4. Verifica que la cita sigue ahí después del despliegue

Si la cita sigue ahí, **¡todo está funcionando correctamente!** 🎉

---

## 📝 Resumen de lo que Acabas de Hacer

- ✅ Actualizaste el servicio a **plan Starter** ($7/mes)
  - El servicio **no se duerme** después de 15 minutos
  - Está **siempre activo**
  
- ✅ Creaste un **disco persistente** (1 GB)
  - Los datos se guardan permanentemente
  - No se borran al desplegar o reiniciar
  
- ✅ Configuraste la **variable de entorno** `DATABASE_PATH`
  - El backend ahora guarda la base de datos en el disco persistente

---

## 💰 Costos

- **Plan Starter**: $7/mes
- **Disco Persistente (1 GB)**: Incluido en el plan Starter (hasta cierto tamaño)
- **Total**: ~$7/mes

---

## 🆘 Si Algo Sale Mal

### El servicio no se actualiza a Starter
- Verifica que la tarjeta esté correctamente configurada
- Revisa que no haya problemas de pago en Render

### No puedo crear el disco
- Asegúrate de que el servicio esté en plan Starter (no Free)
- Espera 2-3 minutos después de actualizar el plan

### Los datos aún se borran
- Verifica que `DATABASE_PATH` sea exactamente `/data` (sin espacios)
- Verifica que el disco esté montado correctamente (debería aparecer en la pestaña "Disk")
- Revisa los logs del servicio para ver si hay errores

---

¡Listo! Tu aplicación ahora tiene disco persistente y está siempre activa. 🚀
