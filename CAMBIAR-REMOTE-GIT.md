# 🔄 Cambiar el Remote de Git

Tu carpeta `Psicologa` tiene el remote `origin` apuntando al repositorio antiguo. Necesitas cambiarlo.

---

## ✅ Opción 1: Cambiar el Remote desde la Terminal

Abre PowerShell o Terminal y ejecuta:

```powershell
cd "C:\Users\AIO HP\Desktop\Psicologa"
git remote set-url origin https://github.com/aprendizcoobup/psicologa-app.git
git remote -v
```

Esto cambiará `origin` para que apunte al repositorio correcto.

---

## ✅ Opción 2: Cambiar el Remote desde GitHub Desktop

1. En GitHub Desktop, selecciona el repositorio `psicologa-app` (el que ya está agregado)
2. Ve a **"Repository"** → **"Repository Settings"** (o click derecho → Settings)
3. Ve a la pestaña **"Remote"**
4. Cambia la URL de `origin` a:
   ```
   https://github.com/aprendizcoobup/psicologa-app.git
   ```
5. Guarda los cambios

---

## ✅ Opción 3: Agregar la Carpeta Correcta en GitHub Desktop

Si `psicologa-app` en GitHub Desktop apunta a la carpeta incorrecta:

1. En GitHub Desktop, haz clic en **"File"** → **"Options"** (o **"Preferences"**)
2. Ve a la pestaña **"Git"**
3. Verifica la configuración

O mejor:

1. Haz clic en el dropdown **"Current repository"** (arriba a la izquierda)
2. Si ves `Psicologa` en la lista, selecciónala
3. Si NO la ves, haz clic en **"Add"** → **"Add Existing Repository"**
4. Navega a: `C:\Users\AIO HP\Desktop\Psicologa`
5. Selecciona la carpeta y haz clic en **"Add"**

---

## 🔍 Verificar

Después de cambiar, verifica:

```powershell
cd "C:\Users\AIO HP\Desktop\Psicologa"
git remote -v
```

Deberías ver:
```
origin  https://github.com/aprendizcoobup/psicologa-app.git (fetch)
origin  https://github.com/aprendizcoobup/psicologa-app.git (push)
```

---

## 📝 Después de Cambiar

1. Haz un `git fetch origin` para sincronizar
2. Verifica que GitHub Desktop muestre los cambios correctos
3. Haz commit y push normalmente

---

¡Esto debería solucionar el problema!
