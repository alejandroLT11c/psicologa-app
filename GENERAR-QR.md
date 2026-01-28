# 📱 Cómo Generar los Códigos QR

Guía paso a paso para generar los dos códigos QR (usuario y administrador).

---

## 🌐 Paso 1: Obtener las URLs

Primero necesitas las URLs de tu aplicación desplegada en Render:

### URL del Frontend (Usuario)
```
https://tu-frontend-url.onrender.com
```
**Ejemplo:** `https://psicologa-frontend-xxxx.onrender.com`

### URL del Frontend (Administrador)
```
https://tu-frontend-url.onrender.com?admin=true
```
**Ejemplo:** `https://psicologa-frontend-xxxx.onrender.com?admin=true`

⚠️ **Importante:** Reemplaza `tu-frontend-url` con la URL real de tu servicio de Static Site en Render.

---

## 🔵 Paso 2: Generar QR de Usuario

### Opción A: Generador Online (Recomendado)

1. Ve a: **https://www.qr-code-generator.com/**
2. En la sección **"URL"**, pega tu URL del frontend (sin `?admin=true`)
3. Haz clic en **"Create QR Code"** o **"Generar"**
4. Descarga el QR en formato PNG o SVG
5. Imprime o comparte el código QR

### Opción B: Google Charts API (Gratis)

Usa esta URL en tu navegador (reemplaza `TU_URL`):
```
https://chart.googleapis.com/chart?cht=qr&chs=300x300&chl=https://tu-frontend-url.onrender.com
```

Luego:
- Haz clic derecho en la imagen → **"Guardar imagen como..."**
- Guarda el QR

### Opción C: Usando el archivo HTML incluido

Si tienes el archivo `generate-qr.html` en tu proyecto:
1. Ábrelo en tu navegador
2. Ingresa la URL del usuario
3. Haz clic en "Generar QR"
4. Descarga o imprime el código

---

## 🔴 Paso 3: Generar QR de Administrador

Sigue los mismos pasos del Paso 2, pero usa la URL **con** `?admin=true`:

### Ejemplo con Google Charts API:
```
https://chart.googleapis.com/chart?cht=qr&chs=300x300&chl=https://tu-frontend-url.onrender.com?admin=true
```

---

## 📋 Paso 4: Verificar las URLs

Antes de generar los QR, verifica que las URLs funcionen:

1. **URL Usuario**: Abre en el navegador → Debe cargar directamente sin login
2. **URL Admin**: Abre en el navegador → Debe mostrar el formulario de login

---

## 🖨️ Paso 5: Imprimir los QR

### Recomendaciones:
- **Tamaño mínimo**: 2 cm x 2 cm (para que se escanee fácilmente)
- **Tamaño recomendado**: 5 cm x 5 cm o más grande
- **Calidad**: Usa alta resolución (300 DPI mínimo)
- **Contraste**: Asegúrate de que haya buen contraste (negro sobre blanco)

### Dónde colocar:
- **QR Usuario**: En lugares públicos, folletos, carteles, etc.
- **QR Admin**: Solo para la administradora (mantener privado)

---

## 🛠️ Generadores de QR Recomendados

### Gratuitos:
1. **QR Code Generator** - https://www.qr-code-generator.com/
2. **QRCode Monkey** - https://www.qrcode-monkey.com/
3. **Google Charts API** - (método directo con URL)

### Con más opciones de diseño:
1. **QR Code Generator** - Permite personalizar colores y logos
2. **QRCode Monkey** - Permite agregar imágenes en el centro

---

## 📱 Probar los QR

Después de generar los QR:

1. **Escanea el QR de usuario** con tu celular
   - Debe abrir directamente la aplicación
   - No debe pedir login
   - Debe mostrar el calendario

2. **Escanea el QR de administrador** con tu celular
   - Debe mostrar el formulario de login
   - Debe pedir usuario y contraseña

---

## ⚠️ Notas Importantes

- **URLs permanentes**: Las URLs de Render son permanentes, así que los QR seguirán funcionando
- **Actualizar QR**: Si cambias la URL del frontend, necesitarás generar nuevos QR
- **Privacidad**: El QR de administrador debe mantenerse privado y seguro

---

## 🎯 Ejemplo Completo

Si tu frontend está en: `https://psicologa-frontend-abc123.onrender.com`

### QR Usuario:
```
https://chart.googleapis.com/chart?cht=qr&chs=500x500&chl=https://psicologa-frontend-abc123.onrender.com
```

### QR Admin:
```
https://chart.googleapis.com/chart?cht=qr&chs=500x500&chl=https://psicologa-frontend-abc123.onrender.com?admin=true
```

Copia estas URLs en tu navegador para ver los QR, luego guárdalos.

---

¡Listo! Ya tienes tus códigos QR generados. 🎉
