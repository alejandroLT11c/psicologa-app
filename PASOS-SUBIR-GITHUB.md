# 📤 Pasos para Subir el Proyecto a GitHub

Esta guía te ayudará a subir tu proyecto a GitHub para luego conectarlo con Render.

---

## ✅ Paso 1: Inicializar Git (Ya hecho automáticamente)

El proyecto ya está preparado con Git. Solo necesitas seguir los siguientes pasos.

---

## 📝 Paso 2: Crear el Repositorio en GitHub

### 2.1 Ir a GitHub
1. Abre tu navegador y ve a: https://github.com/new
2. Inicia sesión con tu cuenta: `aprendizcoobup@gmail.com`

### 2.2 Crear el Repositorio
1. **Repository name**: `psicologa-app` (o el nombre que prefieras)
2. **Description**: "Aplicación web para gestión de citas psicológicas"
3. **Visibility**: 
   - ✅ **Público** (si usas plan gratuito de Render)
   - ⚠️ **Privado** (solo si tienes plan de pago en Render)
4. **NO marques** "Add a README file"
5. **NO marques** "Add .gitignore" (ya lo tenemos)
6. **NO marques** "Choose a license"
7. Click en **"Create repository"**

### 2.3 Copiar la URL del Repositorio
Después de crear el repositorio, GitHub te mostrará una página con instrucciones.
**Copia la URL** que aparece, será algo como:
```
https://github.com/aprendizcoobup/psicologa-app.git
```

---

## 🔄 Paso 3: Conectar el Proyecto Local con GitHub

### Opción A: Usando GitHub Desktop (Más Fácil) ⭐ RECOMENDADO

1. **Descargar GitHub Desktop** (si no lo tienes):
   - Ve a: https://desktop.github.com
   - Descarga e instala GitHub Desktop

2. **Abrir el Proyecto en GitHub Desktop**:
   - Abre GitHub Desktop
   - Click en **"File"** → **"Add Local Repository"**
   - Navega a: `C:\Users\AIO HP\Desktop\Psicologa`
   - Click en **"Add Repository"**

3. **Conectar con GitHub**:
   - En GitHub Desktop, verás un botón **"Publish repository"**
   - Click en **"Publish repository"**
   - Selecciona el repositorio que creaste: `psicologa-app`
   - Asegúrate de que esté marcado como **"Public"** (si usas plan gratuito)
   - Click en **"Publish Repository"**

4. **Hacer el Primer Commit**:
   - GitHub Desktop detectará todos los archivos
   - En la parte inferior, escribe un mensaje: `"Primera versión de la aplicación"`
   - Click en **"Commit to main"**
   - Click en **"Push origin"** (si no se hizo automáticamente)

### Opción B: Usando Git en la Terminal

Abre PowerShell o Terminal en la carpeta del proyecto y ejecuta:

```powershell
# Ir a la carpeta del proyecto
cd "C:\Users\AIO HP\Desktop\Psicologa"

# Inicializar Git (si no está inicializado)
git init

# Agregar todos los archivos
git add .

# Hacer el primer commit
git commit -m "Primera versión de la aplicación"

# Conectar con GitHub (reemplaza TU-USUARIO con aprendizcoobup)
git remote add origin https://github.com/aprendizcoobup/psicologa-app.git

# Cambiar a rama main
git branch -M main

# Subir el código
git push -u origin main
```

---

## ✅ Paso 4: Verificar que Funcionó

1. Ve a tu perfil de GitHub: https://github.com/aprendizcoobup
2. Deberías ver el repositorio `psicologa-app`
3. Click en el repositorio
4. Deberías ver todos tus archivos (app.js, index.html, backend/, etc.)

---

## 🎯 Siguiente Paso

Una vez que el código esté en GitHub, sigue la guía `GUIA-RECREAR-SERVICIOS-EMPRESA.md` para crear los servicios en Render.

---

## ❓ ¿Problemas?

**Error: "Repository not found"**
- Verifica que el nombre del repositorio sea correcto
- Verifica que hayas iniciado sesión en GitHub Desktop o Git

**Error: "Permission denied"**
- Verifica que hayas iniciado sesión en GitHub
- Si usas Git en terminal, puede que necesites configurar tus credenciales

**No veo el botón "Publish repository"**
- Asegúrate de haber agregado el repositorio local primero
- Verifica que Git esté inicializado en la carpeta

---

¡Listo! Una vez que el código esté en GitHub, podrás conectarlo con Render. 🚀
