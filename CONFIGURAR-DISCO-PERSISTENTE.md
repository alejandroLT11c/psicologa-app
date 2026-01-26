# 💾 Configurar Disco Persistente en Render

Este archivo explica cómo configurar un disco persistente en Render para que la base de datos SQLite no se borre cuando se despliega o reinicia el servicio.

## ⚠️ Problema Actual

Cada vez que Render despliega una nueva versión o reinicia el servicio, la base de datos SQLite se borra porque está en el sistema de archivos efímero.

## ✅ Solución: Disco Persistente

### Paso 1: Configurar el Disco Persistente en Render

1. Ve a tu servicio "Psicologa-Backend" en Render
2. En el menú izquierdo, haz clic en **"Disk"**
3. Haz clic en **"Create Disk"** o **"Add Disk"**
4. Configuración:
   - **Name**: `database-disk` (o el nombre que prefieras)
   - **Mount Path**: `/data` (o `/persistent`, el que prefieras)
   - **Size**: `1 GB` es suficiente (puedes aumentar después si es necesario)
5. Haz clic en **"Create"**

### Paso 2: Configurar la Variable de Entorno

1. En tu servicio "Psicologa-Backend", ve a **"Environment"**
2. Haz clic en **"Add Environment Variable"**
3. Agrega:
   - **Key**: `DATABASE_PATH`
   - **Value**: `/data` (o el mismo path que usaste en el Mount Path)
4. Haz clic en **"Save Changes"**

### Paso 3: Reiniciar el Servicio

1. Ve a la pestaña **"Events"** o **"Manual Deploy"**
2. Haz clic en **"Manual Deploy"** → **"Deploy latest commit"**
3. Espera a que termine el despliegue

## 🎯 Resultado

Después de estos pasos:
- ✅ La base de datos se guardará en el disco persistente
- ✅ No se borrará cuando se despliegue una nueva versión
- ✅ No se borrará cuando el servicio se reinicie
- ✅ Los datos (citas, usuarios, días deshabilitados) se mantendrán

## 📝 Notas Importantes

- El disco persistente tiene un costo adicional en Render (verifica los precios actuales)
- El plan gratuito puede tener limitaciones en el tamaño del disco
- Si cambias el `Mount Path`, actualiza también la variable de entorno `DATABASE_PATH`

## 🔄 Verificar que Funciona

1. Después de configurar, crea una cita o deshabilita un día
2. Ve a **"Manual Deploy"** y despliega de nuevo
3. Verifica que los datos siguen ahí después del despliegue

---

**¿Problemas?** Si después de configurar el disco persistente los datos aún se borran, verifica:
- Que el `Mount Path` y `DATABASE_PATH` sean exactamente iguales
- Que el servicio se haya reiniciado después de agregar la variable de entorno
- Los logs del servicio para ver si hay errores al acceder a la base de datos

