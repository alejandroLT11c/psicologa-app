# 💾 Configurar el Disco Persistente (Ya tienes Plan Starter)

Ya tienes el plan Starter activado. Ahora solo necesitas **configurar** el disco persistente (no se compra por separado, ya está incluido en tu plan).

---

## ✅ Paso 1: Crear el Disco Persistente

1. En tu servicio **"Psicologa-Backend"** en Render
2. En el menú izquierdo, haz clic en **"Disk"** (debería tener un ícono de rayo ⚡)
3. Haz clic en **"Create Disk"** o **"Add Disk"**
4. Configuración:
   - **Mount Path**: `/var/data` (o `/data` - Render puede sugerir `/var/data`, ambos funcionan)
   - **Size**: Selecciona **"1 GB"** (cambia de "10 GB" a "1 GB" para ahorrar - es suficiente para SQLite)
5. Haz clic en **"Add Disk"**

**Espera 1-2 minutos** mientras Render crea y monta el disco.

---

## 🔧 Paso 2: Configurar la Variable de Entorno

1. En el menú izquierdo, haz clic en **"Environment"**
2. Haz clic en **"Add Environment Variable"**
3. Agrega:
   - **Key**: `DATABASE_PATH`
   - **Value**: `/var/data` (o `/data` - debe ser **exactamente igual** al Mount Path que usaste al crear el disco)
4. Haz clic en **"Save Changes"**

---

## 🔄 Paso 3: Reiniciar el Servicio

Para que los cambios surtan efecto:

1. Ve a la pestaña **"Events"** o **"Manual Deploy"**
2. Haz clic en **"Manual Deploy"** → **"Deploy latest commit"**
3. Espera a que termine el despliegue (2-5 minutos)

---

## ✅ Paso 4: Verificar que Funciona

1. Después del despliegue, abre tu aplicación
2. Crea una cita de prueba
3. Ve a Render → **"Manual Deploy"** → despliega de nuevo
4. Verifica que la cita sigue ahí después del despliegue

Si la cita sigue ahí, **¡todo está funcionando correctamente!** 🎉

---

## 📝 ¿Por qué no se "compra" el disco?

El disco persistente **NO es un producto separado**. Es una **característica** que viene incluida con el plan Starter. Lo que haces es:

- ✅ **Configurarlo** (crear el disco y montarlo)
- ✅ **Configurar la variable de entorno** (para que el backend sepa dónde guardar)
- ✅ **Reiniciar** (para aplicar los cambios)

No hay costo adicional por el disco (hasta cierto tamaño, que es más que suficiente para tu aplicación).

---

## 🆘 Si Algo Sale Mal

### No veo la opción "Disk"
- Asegúrate de que el servicio esté en plan Starter (no Free)
- Espera 2-3 minutos después de actualizar el plan
- Refresca la página

### No puedo crear el disco
- Verifica que el servicio esté en plan Starter
- Revisa que no haya errores en la consola del navegador

### Los datos aún se borran
- Verifica que `DATABASE_PATH` sea exactamente `/data` (sin espacios, sin comillas)
- Verifica que el disco esté montado (debería aparecer en la pestaña "Disk")
- Revisa los logs del servicio para ver si hay errores al acceder a la base de datos

---

¡Listo! Con estos 3 pasos tendrás el disco persistente funcionando. 🚀
