# 🔐 Solución: Problema de Autenticación con Git

Git está intentando usar las credenciales de otra cuenta. Aquí tienes las soluciones:

## ✅ Opción 1: Usar GitHub Desktop (MÁS FÁCIL) ⭐ RECOMENDADO

1. **Descargar GitHub Desktop** (si no lo tienes):
   - Ve a: https://desktop.github.com
   - Descarga e instala

2. **Abrir el Proyecto**:
   - Abre GitHub Desktop
   - Click en **"File"** → **"Add Local Repository"**
   - Navega a: `C:\Users\AIO HP\Desktop\Psicologa`
   - Click en **"Add Repository"**

3. **Publicar en GitHub**:
   - Verás un botón **"Publish repository"** en la parte superior
   - Click en **"Publish repository"**
   - Asegúrate de que:
     - El nombre sea: `psicologa-app`
     - Esté marcado como **"Public"** (si usas plan gratuito de Render)
   - Click en **"Publish Repository"**

4. **¡Listo!** El código se subirá automáticamente.

---

## 🔧 Opción 2: Configurar Autenticación en Git

Si prefieres usar Git desde la terminal:

### Paso 1: Limpiar credenciales guardadas

1. Abre PowerShell como Administrador
2. Ejecuta:
```powershell
git config --global --unset credential.helper
```

### Paso 2: Usar Personal Access Token

1. **Crear un Token en GitHub**:
   - Ve a: https://github.com/settings/tokens
   - Click en **"Generate new token"** → **"Generate new token (classic)"**
   - Nombre: `psicologa-app-token`
   - Selecciona permisos: ✅ **repo** (todos los permisos de repositorio)
   - Click en **"Generate token"**
   - **⚠️ COPIA EL TOKEN** (solo se muestra una vez)

2. **Usar el Token al hacer push**:
   - Cuando Git te pida usuario y contraseña:
     - **Usuario**: `aprendizcoobup`
     - **Contraseña**: Pega el token que copiaste

### Paso 3: Hacer push de nuevo

```powershell
cd "C:\Users\AIO HP\Desktop\Psicologa"
git push -u origin main
```

---

## 🎯 Recomendación

**Usa GitHub Desktop** - Es mucho más fácil y no necesitas manejar tokens ni credenciales manualmente.

---

¿Necesitas ayuda con alguno de estos métodos?
