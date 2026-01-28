# 🔄 Cambiar Repositorio en Render - Paso a Paso

Como Render solo muestra repositorios de `alejandroLT11c`, usa la opción "Public Git Repository" para conectar `aprendizcoobup/psicologa-app`.

---

## ✅ Paso 1: Usar "Public Git Repository"

En la pantalla que estás viendo:

1. **Baja hasta la sección "Public Git Repository"** (está más abajo en la página)
2. Verás un campo de texto con un ejemplo de URL
3. **Borra el ejemplo** y pega esta URL:
   ```
   https://github.com/aprendizcoobup/psicologa-app
   ```
4. Haz clic en **"Continue"** o **"Save"**

---

## ✅ Paso 2: Configurar Branch y Build Commands

Después de conectar el repositorio, Render te pedirá:

1. **Branch**: Selecciona `main` (o `master` si es el que tienes)
2. **Root Directory**: Déjalo vacío (o pon `backend` si Render lo requiere)
3. **Build Command**: `cd backend && npm install`
4. **Start Command**: `cd backend && node server.js`

---

## ✅ Paso 3: Repetir para el Frontend

1. Ve a tu servicio **Static Site** en Render
2. Ve a **Settings** → **Repository**
3. Baja hasta **"Public Git Repository"**
4. Pega la misma URL: `https://github.com/aprendizcoobup/psicologa-app`
5. Haz clic en **"Continue"**
6. Configura:
   - **Branch**: `main`
   - **Build Command**: `echo "No build needed"`
   - **Publish Directory**: `.` (punto)

---

## ⚠️ Importante

- El repositorio `aprendizcoobup/psicologa-app` debe ser **público** para que funcione esta opción
- Si es privado, necesitarás conectar la cuenta de GitHub `aprendizcoobup` a Render primero

---

## 🔍 Verificar que el Repositorio es Público

1. Ve a: https://github.com/aprendizcoobup/psicologa-app
2. Si ves un candado 🔒 = Es privado
3. Si NO ves candado = Es público ✅

Si es privado, tendrás que:
- Conectar la cuenta `aprendizcoobup` a Render, O
- Hacer el repositorio público temporalmente

---

¡Después de esto, ya no necesitarás copiar archivos manualmente! 🎉
